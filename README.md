# Programación de y con Agentes de IA — MBA UCEMA

Materia del MBA de la Universidad del CEMA, dictada por Alfredo B. Roisenzvit. Segundo trimestre de 2026.

Este repositorio es la cara pública de un experimento docente: una materia de posgrado **sobre** agentes de IA, construida y dictada **con** agentes de IA, contada en abierto mientras ocurre. Acá se publica el material que va saliendo de la cursada: los hilos de la serie, los videos, y el agente de presentación de cada clase.

La serie se puede seguir en X y LinkedIn con el hashtag **#ucemaAGENTES**.

## La apuesta

La materia propone un cambio total de paradigma en la enseñanza formal, y por tanto está construida para vivir a la altura del nuevo paradigma.

No hay PowerPoint: cada clase se dicta con un **agente de presentación**, un programa construido específicamente para la materia que ejecuta herramientas en vivo mientras se dicta. No se enseña a instalar nada: cualquier instructivo dictado hoy vence antes de que termine el trimestre, así que lo que se enseña es la competencia que no vence — investigar la propia herramienta con la IA como tutor. Y una regla atraviesa todo el programa: **nunca se afirma que la IA no puede hacer algo**; cuando un resultado no aparece, la pregunta profesional es cómo se lo estamos pidiendo.

La trastienda también es parte del argumento: el campus virtual se genera por código, el material de clase lo mantiene un agente, los textos de la serie los redacta un agente entrenado en el criterio editorial del profesor — con revisión humana en un solo punto, la aprobación final. Hasta el proyecto final de la materia es agéntico: los estudiantes construyen el agente que corrige el trabajo final, y son evaluados por él y por cómo lo construyeron.

## Qué hay acá

```
deck/     el agente de presentación de cada clase — un archivo HTML:
          abrilo en el navegador y avanzá con la barra espaciadora
assets/   videos y capturas del material
hilos/    los hilos publicados de la serie, con fecha y link
fichas/   las fichas de presentación de los estudiantes
```

## Cómo subir tu ficha

Tu primera entrega es tu ficha de presentación, y se sube con el mismo mecanismo que usan los equipos de software de todo el mundo: un *pull request*. Todo se hace desde el navegador, sin instalar nada. Necesitás una cuenta de GitHub (se crea gratis en [github.com/signup](https://github.com/signup)) y haber iniciado sesión.

1. **Abrí la plantilla.** Entrá a la carpeta [`fichas/`](fichas/) de este repositorio y hacé clic en el archivo `_plantilla.md`. Ese es el modelo de tu ficha: leelo para ver los tres campos que vas a completar.

2. **Creá tu archivo.** Volvé a la carpeta [`fichas/`](fichas/) y arriba a la derecha buscá el botón **Add file** → **Create new file**. En el casillero del nombre escribí tu nombre en minúsculas y con guiones, terminado en `.md` — por ejemplo: `ana-garcia.md`.

3. **Completá tu ficha.** En el cuadro grande de texto, copiá los tres títulos de la plantilla y escribí tu respuesta debajo de cada uno: **Nombre y apellido**, **A qué me dedico**, y **Qué proceso de mi trabajo le delegaría a un agente**.

4. **Proponé el cambio.** Hacé clic en el botón verde **Commit changes...**. GitHub te va a avisar que no podés escribir directamente en este repositorio y te va a proponer crear una copia (*fork*) con tu cambio en una rama nueva: aceptá lo que te propone tal como viene y confirmá con **Propose changes**.

5. **Abrí tu pull request.** En la pantalla siguiente, hacé clic en el botón verde **Create pull request** (dos veces, si te lo vuelve a pedir). Listo: tu ficha quedó propuesta. No podés romper nada — un pull request es exactamente eso, una propuesta que el profesor revisa y aprueba. Cuando se apruebe, tu ficha va a aparecer en la carpeta `fichas/` junto a las de tus compañeros.

Si algo salió distinto de lo que esperabas, la regla de la materia aplica acá también: pedile a tu IA de confianza que te guíe — contale en qué pantalla estás y qué querés lograr.

## El agente de presentación

`deck/clase1_agente.html` es la primera clase completa. No es una exportación: es el programa que se usó para dictarla. Un único archivo, quince escenas declarativas, un motor que las revela paso a paso, y llamadas a herramientas que se ejecutan en pantalla. Se edita como texto y se versiona acá, como cualquier pieza de software.

En `assets/deck-clase1.mp4` hay un recorrido de 48 segundos, generado — también — por un agente que ejecuta la presentación, la graba y la recorta sin intervención manual.

---

Alfredo B. Roisenzvit — UCEMA
