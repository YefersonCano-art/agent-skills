# Ejemplos de uso

## Ejemplo 1: Solicitud estándar

### Input del usuario

"Dame un Reporte Ejecutivo-Técnico del Repositorio."

### Comportamiento esperado

- Crear documento en `docs/` con fecha
- Usar las 7 secciones obligatorias
- Incluir ramas principales y secundarias por separado
- Incluir stack y dependencias con versiones

---

## Ejemplo 2: Solicitud con énfasis en ramas

### Input del usuario

"Quiero saber cuáles son las ramas principales y cuáles las secundarias."

### Comportamiento esperado

- No llamar obsoleta a `main` ni a otras ramas principales
- Separar la lectura de ramas por rol
- Sugerir acciones distintas para base estable vs ramas temporales

---

## Ejemplo 3: CI/CD no detectado

### Input del usuario

"Incluye CI/CD en el análisis."

### Comportamiento esperado

- Incluir sección 7 siempre
- Si no se detectan workflows o pipelines, declararlo explícitamente
- No inventar integración continua

---

## Checklist rápido antes de entregar

- ¿El reporte tiene las 7 secciones en el orden correcto?
- ¿Separaste ramas principales y secundarias?
- ¿Evitaste llamar obsoleta a una rama principal?
- ¿Incluiste stack y dependencias con versión y propósito?
- ¿La sección de CI/CD existe aunque no haya evidencia?
