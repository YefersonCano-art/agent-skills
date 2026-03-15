# reporte-repositorio

Skill de reporte ejecutivo-técnico de repositorio para agentes.

## Qué hace

Genera un reporte técnico-ejecutivo de 7 secciones cuando el usuario lo solicita explícitamente.

- Guarda la salida en `docs/`.
- Separa ramas principales y secundarias.
- Incluye colaboración, dependencias, arquitectura y CI/CD (si aplica).

## Activación

Este skill debe activarse solo en solicitudes explícitas de reporte, por ejemplo:

- "dame un reporte del repositorio"
- "genera un reporte del repo"
- "reporte ejecutivo-técnico del repositorio"

## Instalación

```bash
npx skills add https://github.com/YefersonCano-art/agent-skills --skill reporte-repositorio
```

## Actualización

Ejecuta el mismo comando de instalación para refrescar la skill con la última versión del repositorio.

## Archivos de la skill

- `SKILL.md`
- `SKILL.json`
- `template.md`
- `patterns.md`
- `examples.md`
