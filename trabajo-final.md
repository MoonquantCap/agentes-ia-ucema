# Trabajo final — Un sistema agéntico para un caso real

**Programación de y con Agentes de IA** · MBA UCEMA · 2026 2T · Prof. Alfredo B. Roisenzvit

**Individual · Se entrega: domingo 13/9, 23:59 · Corrección: por el agente evaluador de la materia, elegido en la última clase**

---

## Qué es

El trabajo final es un **sistema agéntico completo aplicado a un caso real** de tu trabajo, tu negocio o tu interés — la versión seria de lo que empezaste en la Entrega 1. No es un chatbot ni un prompt suelto: es un agente con objetivo, contrato, herramientas y supervisión definida, que corre de verdad sobre datos reales.

**Quién lo corrige:** un único agente. En la última clase (jueves 10/9), cada grupo somete su evaluador a la prueba de fuego en vivo — y de esa prueba sale elegido **el agente evaluador de la materia**: uno solo, el que mejor corrige. Ese agente corrige **todos** los trabajos finales después del cierre, y los resultados se publican en el campus. Todos son evaluados por la misma vara — una vara que construyeron ustedes. Los desacuerdos los arbitra el profesor.

## Los seis requisitos

**1 · Un sistema completo.** Objetivo claro, contrato escrito (system prompt + user prompt, con las seis piezas), **al menos una herramienta o conector real** (una API, archivos, una planilla, un calendario), salida en formato estructurado, y puntos de supervisión humana definidos con el vocabulario del curso (L0–L4: qué hace solo, qué revisa una persona, quién firma).

**2 · Corre de verdad.** Evidencia de **al menos tres corridas reales** con entradas reales, guardadas tal como salieron. Un tercero (humano o agente) tiene que poder reconstruir qué pasó en cada corrida.

**3 · Formato estricto.** La corrección la hace un agente: si no puede leer tu repo, no puede corregirlo — y eso es una lección del curso, no una injusticia. Estructura obligatoria:

```
README.md        — el README estándar de la materia
prompts/         — system_prompt.md, user_prompt.md (y variantes si las hay)
corridas/        — las tres ejecuciones: entrada, salida, fecha
DECISIONES.md    — la historia: iteraciones, qué falló, qué se achicó y por qué
```

**4 · La historia del proceso.** `DECISIONES.md` cuenta cómo llegaste: las iteraciones del contrato, los errores textuales, los cambios de alcance. Ya conocés la casa: el proceso documentado es el corazón de la nota.

**5 · Análisis económico.** Qué cuesta una corrida (tokens de entrada y salida), qué costaría el sistema corriendo en serio (por semana, por año), y la elección de modelo justificada con el criterio del curso: el más chico que hace bien la tarea.

**6 · Gobierno y riesgo.** Qué sistemas toca tu agente y con qué permisos, qué puede salir mal y qué pasa cuando sale mal, qué revisás vos antes de confiar en una salida, y quién firma el resultado.

## La rúbrica oficial

Esta es la rúbrica que los agentes evaluadores del parcial vuelven ejecutable y aplican en vivo:

| Dimensión | Peso |
| --- | --- |
| Sistema completo y funcionando: contrato, herramienta real, output estructurado, supervisión definida | 30 |
| Proceso documentado: iteraciones, fallas, decisiones — la historia real de la construcción | 25 |
| Formato y reproducibilidad: estructura obligatoria respetada, corridas reconstruibles | 15 |
| Análisis económico: costo por corrida, proyección, elección de modelo justificada | 15 |
| Gobierno y riesgo: permisos, fallas posibles, supervisión, quién firma | 15 |

Como en toda la materia: **un sistema honesto con una falla bien contada vale más que uno pulido que no se entiende.** El evaluador que te corrija fue construido sobre esa misma filosofía — por tus propios compañeros.

## Escala y consejos

La escala correcta es «el mejor proyecto que se puede construir en dos semanas y media de atención parcial»: más ambicioso que la Entrega 1, más chico que un producto. Elegí un caso que te importe — los mejores trabajos de la Entrega 1 fueron los que resolvían un problema propio. Si no se te ocurre el caso, ya sabés: pedile ideas al agente (el prompt está en el campus). Y arrancá esta semana: las tres corridas reales y la calibración de tu documentación llevan más tiempo del que parece.

## Entrega

Subí el **link a tu repositorio público** en la actividad *Trabajo final* del campus, antes del **domingo 13 de septiembre, 23:59**. La última clase (jueves 10/9) te sirve de checkpoint: llevá tu avance, que esa noche se elige al evaluador que va a corregirte. Sin excepciones de formato: el agente que te corrige no improvisa.
