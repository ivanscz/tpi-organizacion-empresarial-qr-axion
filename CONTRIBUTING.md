# Guía de contribución

## Ramas
- `main`: versión revisada. No se trabaja directamente sobre ella.
- `docs/<tema>`: cambios de documentación (por ejemplo `docs/backlog-e-indicadores`).
- `feature/<tema>`: modelos o artefactos nuevos (por ejemplo `feature/modelado-bpmn`).

## Mensajes de commit
Formato: `tipo: descripción en presente y en minúsculas`

| Tipo | Uso |
|---|---|
| `docs` | Documentación (entregas, diccionario, historias, indicadores, README) |
| `feat` | Artefacto nuevo (por ejemplo el diagrama BPMN) |
| `fix` | Corrección de un error en un documento o diagrama |
| `chore` | Tareas de mantenimiento del repositorio |

Ejemplo: `docs: definir las tres historias de usuario con criterios de aceptación`

## Pull Requests
1. Abrir el PR desde la rama secundaria hacia `main` usando la plantilla.
2. Pedir la revisión de otra persona.
3. Resolver los comentarios y recién entonces hacer el merge.
