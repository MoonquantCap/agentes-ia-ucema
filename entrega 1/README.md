# Entrega 1

Dos agentes generados en la cursada:

## `nutricion-agente/`

Corpus de 50 papers con referato (2021–2026) sobre nutrición clínica y microbiota/metabolismo, investigados y verificados para armar la base de conocimiento de un agente nutricionista. Incluye:
- `corpus-nutricional.html` — listado navegable con buscador y filtros por tema/acceso abierto.
- `papers/` — 15 PDFs de los papers de acceso abierto que pudieron descargarse automáticamente (los editores que bloquean scraping quedan como link directo dentro del listado).

## `plan-comidas/`

Agente que arma un plan semanal de batch cooking (5 almuerzos + 5 cenas) a partir de gustos y restricciones personales, con lista de compras georreferenciada a comercios reales cercanos al domicilio del usuario y costo estimado. Incluye:
- `semana-batch-cooking.html` — plan con recetas completas y cronograma de producción.
- `semana-batch-cooking.md` — mismo contenido en Markdown.

El plan se regenera automáticamente todos los domingos mediante una rutina programada (agente en la nube).
