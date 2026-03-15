# Patrones del Reporte Ejecutivo-Técnico

## Patrón 1: Orden fijo del reporte

El reporte siempre debe usar este orden, sin omitir secciones:

1. Resumen ejecutivo
2. Panorama general
3. Estructura del repositorio
4. Estado de ramas y colaboración
5. Tecnologías y dependencias
6. Arquitectura de la aplicación
7. CI/CD (si aplica)

No reemplazar esta estructura por una versión corta.

---

## Patrón 2: Clasificación de ramas por rol

### Ramas principales

Considera principales, salvo evidencia contraria:

- `main`
- `master`
- `develop`
- `dev`
- `trunk`
- `release/*`
- `staging`
- `production`

Lecturas sugeridas:

- "Base principal del repositorio"
- "Rama de integración"
- "Sin actividad reciente"
- "Requiere validación de vigencia"

Nunca usar "obsoleta" para una rama principal.

### Ramas secundarias

Ejemplos:

- `feature/*`
- `fix/*`
- `hotfix/*`
- `bugfix/*`
- `chore/*`
- `docs/*`
- `refactor/*`
- `test/*`
- ramas personales

Estados sugeridos:

- `Activa`
- `En pausa`
- `Candidata a cierre`

---

## Patrón 3: Lectura de contribuyentes

Usa 30/90 días por defecto para evitar sesgo de semanas aisladas.

Tendencias sugeridas:

- `Sube`: 30 días con señal de recuperación o incremento frente al periodo largo.
- `Baja`: sin actividad reciente o caída evidente.
- `Estable`: aporte sostenido.
- `Sin actividad reciente`: cero commits en 30 y 90 días.

---

## Patrón 4: Stack y dependencias

Siempre separar al menos:

- Dependencias de runtime
- Dependencias de desarrollo
- Versiones críticas
- Propósito de uso

No listar paquetes irrelevantes sin contexto. Prioriza frameworks, routing, estado, UI, build, linting, testing y despliegue.

---

## Patrón 5: CI/CD

La sección 7 siempre debe existir.

Si hay evidencia, incluir:

- Pipelines o workflows
- Archivos de despliegue
- Integraciones visibles
- Automatizaciones de build, test o deploy

Si no hay evidencia, escribir explícitamente:

- "No se detectó pipeline CI/CD en el repositorio analizado."

---

## Patrón 6: Redacción técnica-ejecutiva

- Lenguaje claro, sin adornos.
- Técnica suficiente para onboarding y decisión.
- No convertirlo en auditoría profunda.
- Si falta evidencia, declararlo y no inventar.
