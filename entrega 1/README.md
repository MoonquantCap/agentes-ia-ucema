# Agente Nutricionista

## Qué construí

Un agente nutricionista con dos partes que se apoyan una en la otra: (1) una base de evidencia de 50 papers con referato sobre nutrición clínica y microbiota/metabolismo, verificados uno por uno contra PubMed/PMC para que ningún título o DOI sea inventado, y (2) un agente que corre en la nube todos los domingos y que debería generar solo, sin que yo se lo pida, el plan de comidas de la semana laboral (5 almuerzos + 5 cenas) para batch cooking, con lista de compras georreferenciada a comercios reales cerca de mi casa (Palermo, CABA), costo estimado y receta completa de cada plato. Es para uso personal mío.

La idea completa es: el corpus (1) le da fundamento científico a las decisiones de menú del agente (2), en vez de que el agente invente recomendaciones nutricionales genéricas sin respaldo.

## Cómo se lo pedí

Los pedidos reales, en el orden en que se los hice al agente (Claude Code), textuales:

1. *"quiero crear un agente nutricionista, primero necesito que investigues los mejores 50 papers con referato de las principales universidades del mundo que esten actualizados"*
2. *"Es clave que optimices los recursos"* (mandado mientras el agente ya estaba investigando)
3. *"que paso con los otros que no los descargaste?"*
4. *"podes buscoar otros para completar los 50? asegurando que los que propongas puedas bajar los PDF?"*
5. *"quiero crear un agente nutricionista que en base a mis gustos me arme un plan de alimentación para la semana laboral, donde contemple almuerzo (que se regenra en un microondas) y la cena, armes un listado de compras con los ingredientes (sin contar condimentos) busques en una zona de 15 cuadras a la redonda de mi domicilio (gurruchaga 2271, Palermo, Capital federal) donde comprar los ingredientes en base al precio, podes armar un mix en un maximo de dos lugares y que automaticamente los domingos antes de las 10 am, me generes una lista de compras, con la dirección y el local para realizar la comra, el gasto estimado y la receta para la preparación de las 10 comidas, pensando en el metodo de batch cooking, que no lleve mas de 2 o 3 horas de producción"*
6. *"dale, tambien tiene que tener las recetas que no la estoy viendo en 'semana de batch Cooking'"*
7. *"Me subis el proyecto a mi repositorio de github?"*

En los primeros dos pedidos, el agente no arrancó directo: antes de investigar me preguntó alcance temático, ventana de tiempo y formato de entrega; antes de armar el plan de comidas me preguntó restricciones alimentarias, variedad deseada, prioridad de compra y equipamiento de cocina. No asumió gustos que no tenía forma de saber.

El prompt final que quedó corriendo solo, cargado en la rutina programada (no lo escribí yo directamente palabra por palabra — lo armó el agente a partir de mis respuestas a esas preguntas, y lo fui corrigiendo en dos iteraciones), está completo en el archivo `Proceso de la creación`, en esta misma carpeta. Ahí se ve también por qué tiene esa forma: repite mi dirección y restricciones porque cada corrida es una sesión nueva sin memoria de la anterior, y cita papers puntuales del corpus como criterio de diseño del menú (por ejemplo, ~1.6 g de proteína por kg de peso según Nunes et al. 2022, o el patrón mediterráneo de Rinott et al. 2022) para que las decisiones del menú tengan de dónde salir, no sean una recomendación genérica.

## Qué funciona

- **El corpus de papers**: `nutricion-agente/corpus-nutricional.html` — 50 papers reales (verificados individualmente contra PubMed/PMC antes de incluirlos), con buscador y filtro por tema/estado de acceso. De los 30 papers de acceso abierto, 15 PDFs se descargaron automáticamente y se confirmaron como PDF real (chequeo de los primeros bytes del archivo, `%PDF`, no solo que la descarga "no diera error") — están en `nutricion-agente/papers/`.
- **El plan de comidas, generado una vez a mano**: `plan-comidas/semana-batch-cooking.html` y `.md` — un plan completo de 10 comidas con receta paso a paso, lista de compras y cronograma de producción de ~2h45. Los comercios y las distancias caminando (La Peruanita a 0 cuadras, DIA a 1.1 km, etc.) están verificados con Google Maps, no inventados.
- **La publicación en GitHub**: el push a este repositorio funcionó, usando las credenciales que ya tenía guardadas Git Credential Manager en mi máquina.
- Se puede reproducir pidiéndole al agente: "generame el plan de comidas de esta semana" — vuelve a investigar precios y arma un menú nuevo cada vez que se lo pido a mano.

## Qué falta o qué falló

- **Lo central del pedido — que la rutina corra sola todos los domingos — no está confirmado funcionando.** Se creó una rutina programada en la nube (cron, domingos 8:00 AM Argentina) y quedaron registradas dos corridas: una prueba manual (17/08) y una automática real (23/08, disparada sola por el cron). Al revisar el log de las dos, ninguna muestra evidencia de haber ejecutado la tarea de verdad: solo aparece el arranque del entorno ("Allocating sandbox" → "Claude Code process started") y nada más — ni búsquedas de precios, ni el artifact publicado, ni el mensaje final. Es decir: el cron dispara y el entorno se levanta, pero todo indica que el prompt nunca llega a procesarse dentro de la sesión. Esto quedó **sin resolver** al momento de esta entrega.
- **Descarga de PDFs**: antes de encontrar un método que funcionara, probé tres rutas que fallaron: el patrón de URL directa de PubMed Central (`/pdf/`) devuelve error 404 porque el visor nuevo de PMC arma esa URL con JavaScript; el servicio Europe PMC devolvió una conexión vacía; el servicio oficial de NCBI para artículos de acceso abierto devolvió una ruta FTP que ya no existe. El método que sí funcionó (leer la etiqueta `citation_pdf_url` de la página simulando una sesión de navegador) solo sirvió con 2 de las ~8 editoriales que probé (Nature.com y Springer/BMC); BMJ, Wiley, JAMA Network, AHA, MDPI, Elsevier y Taylor & Francis bloquean la descarga aunque el artículo sea de acceso abierto.
- **El costo del plan de comidas es una estimación, no un precio verificado en vivo**: el sitio oficial argentino de comparación de precios (preciosclaros.gob.ar) tiene roto su propio widget de dirección, y otro intento de leer precios directo del sitio de un supermercado no devolvió resultados usables. Se documentó esto explícitamente en el artifact entregado en vez de mostrar un número como si fuera exacto.
- Al crear la rutina automática, el sistema le adjuntó por defecto 3 conectores que no pedí — incluida mi cuenta de un bróker financiero y Google Drive. Los detecté revisando la respuesta de la API y los saqué a mano; una automatización sin supervisión no debería quedar con acceso a herramientas que no usa.

## Qué aprendí

*(Borrador armado por el agente a partir de lo que pasó en la sesión — lo dejo en primera persona para que lo revises y lo hagas tuyo antes de entregarlo, cambiando lo que no sientas como propio.)*

Lo más difícil de construir este agente no fue pedirle que investigue o que arme un menú — eso lo resuelve bien a la primera. Lo difícil fue la verificación: un modelo de lenguaje puede generar un título de paper, un DOI o una dirección de comercio que "suena" perfectamente real sin que exista, así que tuve que insistir en que cada dato se confirmara contra una fuente externa (PubMed, los bytes del archivo descargado, Google Maps) antes de confiar en él. Aprendí también que "crear la rutina automática" y "la rutina funciona" son dos cosas distintas: el sistema me devolvió una confirmación de que la tarea programada quedaba creada, pero solo revisando el log de ejecución (no solo confiando en que "se configuró bien") aparece que probablemente no está corriendo de verdad — si no hubiera ido a mirar esa evidencia, hoy pensaría que el proyecto funciona completo cuando en realidad su pieza central todavía no está probada. Y en un agente que corre sin supervisión, el control de qué herramientas/accesos tiene no es un detalle: apareció conectado a mi cuenta de un bróker sin que yo lo pidiera, y tuve que sacarlo a mano.
