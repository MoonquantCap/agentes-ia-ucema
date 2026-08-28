# Parcial — El agente evaluador

**Programación de y con Agentes de IA** · MBA UCEMA · 2026 2T · Prof. Alfredo B. Roisenzvit

**Grupal (hasta 6 integrantes) · Abre: jueves 27/8, 22:00 · Cierra: miércoles 9/9, 18:59 · Prueba de fuego: en vivo, en la última clase**

---

## Qué es

El parcial de la materia es construir un **agente evaluador**: el sistema que va a corregir, en vivo y frente a todos, los trabajos finales de sus compañeros.

La lógica la vieron en clase: la rúbrica con la que se corrigen sus entregas es un prompt — una especificación ejecutable. Ahora la escriben ustedes. Evaluar bien es definir «bien hecho» con tanta precisión que hasta una máquina puede aplicarlo; el parcial es demostrar esa competencia.

## Las cuatro piezas que entrega cada grupo

**1 · La rúbrica ejecutable.** La rúbrica oficial del trabajo final (publicada en el documento del final) define *qué* dimensiones se evalúan y sus pesos. El trabajo de ustedes es volverla **ejecutable**: escalas por nivel, qué evidencia exige cada puntaje, ejemplos de qué merece un nivel alto y uno bajo en cada dimensión. Tan precisa que un agente la aplica igual dos veces; tan legible que un humano puede discutirla.

**2 · El agente corrector.** El system prompt (más las herramientas que necesite) que recibe un trabajo final real — un repositorio — y devuelve: puntaje por dimensión, justificación breve de cada puntaje citando evidencia del trabajo, y una sugerencia concreta de mejora. Salida en formato estructurado, idéntico en cada corrida.

**3 · Tres casos de prueba.** Tres trabajos de ejemplo construidos por ustedes: uno **excelente**, uno **flojo**, y uno **tramposo** — que intenta engañar al corrector (afirma cosas que no hizo, infla su documentación, apela a la simpatía del evaluador). Su agente tiene que puntuar alto al primero, bajo al segundo, y **detectar al tercero**.

**4 · La calibración.** La evidencia de que las notas del agente coinciden con el criterio humano del grupo sobre esos mismos casos: qué notas puso el agente, qué notas hubieran puesto ustedes, dónde no coincidían, qué ajustaron en la rúbrica o en el corrector, y cómo quedó después del ajuste.

## Estructura obligatoria del repositorio

Un repositorio público de GitHub por grupo, con esta estructura (la corrección la asiste un agente: el formato importa):

```
README.md          — el README estándar de la materia + integrantes del grupo
rubrica.md         — la rúbrica ejecutable
agente/            — system prompt y configuración del corrector
casos/excelente/   — caso de prueba 1
casos/flojo/       — caso de prueba 2
casos/tramposo/    — caso de prueba 3
calibracion.md     — la evidencia de calibración
```

La **historia de commits** debe mostrar el trabajo real del grupo: quién aportó qué, cómo evolucionó la rúbrica. Un repo con un único commit del último día cuenta una historia — y no es buena.

## Cómo se evalúa el parcial

| Criterio | Peso |
| --- | --- |
| Rúbrica ejecutable: precisión, escalas, evidencia exigida por nivel | 25 |
| Agente corrector funcionando: corre sobre un repo real y devuelve el formato completo | 25 |
| Casos de prueba: los tres existen y el corrector los distingue (incluido el tramposo) | 20 |
| Calibración documentada: desacuerdos encontrados, ajustes hechos, resultado | 15 |
| Proceso grupal: historia de commits, iteraciones de la rúbrica, decisiones registradas | 15 |

**La prueba de fuego es pública:** en la última clase, cada agente evaluador corrige en vivo trabajos finales que nunca vio. Un evaluador que se desploma frente a un caso real dice algo sobre su construcción — y la clase entera lo va a ver. Construyan para ese momento.

## Reglas de la casa, aplicadas

Nadie del grupo escribe código: se construye describiendo, iterando y documentando, con la IA como tutor. Si el corrector «no puede» leer un repo, la pregunta es qué herramienta o instrucción le falta. Y el proceso documentado vale: un desacuerdo de calibración honesto y bien resuelto suma más que una calibración perfecta sin historia.

## Entrega

Un integrante sube el **link al repositorio del grupo** en la actividad *Parcial* del campus, antes del **miércoles 9 de septiembre, 18:59**. El Foro de grupos del campus está abierto para armar equipos y coordinar.
