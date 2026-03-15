---
name: reporte-repositorio
description: Se activa solo cuando el usuario solicita explícitamente un reporte del repositorio y genera un Reporte Ejecutivo-Técnico con estructura fija de 7 secciones.
---

# Reporte Ejecutivo-Técnico del Repositorio

## Propósito

Entregar un documento técnico-ejecutivo consistente para entender el estado real de un repositorio sin caer en auditoría profunda. La salida debe servir tanto para toma de decisiones como para onboarding rápido.

## Activación y límites

Usar cuando:

- El usuario solicita explícitamente un **reporte del repositorio**.
- Variantes válidas: "dame un reporte del repositorio", "genera reporte del repo", "reporte ejecutivo-técnico del repositorio".

Evitar cuando:

- El usuario pide debugging puntual o corrección de código.
- El usuario solo quiere buscar archivos o símbolos concretos.
- El usuario pide análisis parciales (por ejemplo, solo ramas o solo dependencias) sin pedir reporte completo.

## Regla principal de esta skill

- Esta skill ya no genera un reporte ejecutivo simple.
- Siempre genera un **Reporte Ejecutivo-Técnico del Repositorio**.
- Siempre usa la **misma estructura completa**.
- No omite secciones por brevedad; si falta información, lo declara explícitamente dentro de la sección correspondiente.

## Regla de entrega (obligatoria)

- El resultado final debe guardarse **siempre** en un archivo Markdown dentro de `docs/`.
- Formato de nombre recomendado: `REPORTE_EJECUTIVO_TECNICO_YYYY-MM-DD.md`.
- El reporte debe incluir explícitamente la fecha de generación.
- Además del archivo, entregar un resumen breve en chat.

## Alcance del reporte (obligatorio)

1. Resumen ejecutivo del proyecto
2. Panorama general
3. Estructura del repositorio
4. Estado de ramas y colaboración
5. Tecnologías y dependencias
6. Arquitectura de la aplicación
7. CI/CD (si aplica)

## Reglas de ramas

### Clasificación de ramas

Clasifica las ramas en dos grupos:

- **Ramas principales**: `main`, `master`, `develop`, `dev`, `trunk`, `release/*`, `staging`, `production` o equivalentes que representen base, integración o entrega.
- **Ramas secundarias**: `feature/*`, `fix/*`, `hotfix/*`, `bugfix/*`, `chore/*`, `docs/*`, `refactor/*`, `test/*` y ramas personales o temporales.

### Regla crítica

- **Nunca** describas una rama principal como “obsoleta”.
- En ramas principales usa lectura operacional, por ejemplo: `Base principal`, `Rama de integración`, `Sin actividad reciente`, `Requiere validación de vigencia`.
- En ramas secundarias puedes usar estados como: `Activa`, `En pausa`, `Candidata a cierre`.

### Datos mínimos por rama

- Nombre
- Tipo (`Principal` o `Secundaria`)
- Última actividad
- Último autor
- Lectura o estado
- Acción sugerida

Si no hay metadata de PR/issue, no inventes contexto; marca `sin evidencia adicional`.

## Reglas de colaboración

Por cada contribuyente incluye:

- Commits en 30 días
- Commits en 90 días
- Tendencia (`Sube`, `Baja`, `Estable`, `Sin actividad reciente`)
- Nivel (`Alta`, `Media`, `Baja`)

Si la actividad está concentrada en 1 o 2 personas, indícalo de forma neutral.

## Flujo de trabajo

1. Levantar contexto del proyecto

- Leer `README`, `package.json`, router principal, carpetas núcleo y archivos de configuración.

2. Levantar datos Git

- Ramas locales/remotas y última actividad.
- Historial corto para contexto reciente.
- Contribuyentes agregados por 30/90 días.

3. Identificar stack y dependencias

- Frameworks, librerías críticas, versiones y propósito.
- Distinguir runtime y desarrollo.

4. Identificar arquitectura y estructura

- Módulos principales.
- Flujo de datos.
- Decisiones técnicas visibles.
- Evidencia de CI/CD si existe.

5. Redactar con la plantilla fija

- Sin simplificar la estructura.
- Sin cambiar el orden de secciones.

6. Guardar documento

- Escribir reporte final en `docs/REPORTE_EJECUTIVO_TECNICO_YYYY-MM-DD.md`.
- Confirmar al usuario la ruta creada o actualizada.

## Formato de salida requerido

Usa siempre esta estructura:

# Reporte Ejecutivo-Técnico del Repositorio

**Fecha:** YYYY-MM-DD
**Repositorio:** NOMBRE_REPOSITORIO
**Fuente de datos:** Git + archivos de NOMBRE_REPOSITORIO

## 1) Resumen ejecutivo

- Qué hace el proyecto
- Para quién es
- Estado actual
- Hallazgos clave

## 2) Panorama general

- Tipo de proyecto
- Estado actual
- Entrypoints / rutas / scripts principales
- Hallazgos operativos relevantes

## 3) Estructura del repositorio

- Árbol resumido de carpetas principales
- Responsabilidades por carpeta
- Convenciones observadas

## 4) Estado de ramas y colaboración

### Ramas principales

| Rama | Tipo | Última actividad | Autor | Lectura | Acción sugerida |
| ---- | ---- | ---------------- | ----- | ------- | --------------- |

### Ramas secundarias

| Rama | Tipo | Última actividad | Autor | Estado | Acción sugerida |
| ---- | ---- | ---------------- | ----- | ------ | --------------- |

### Contribuyentes

Periodo analizado: 30/90 días

| Contribuyente | Commits (30d) | Commits (90d) | Tendencia | Nivel |
| ------------- | ------------: | ------------: | --------- | ----- |

## 5) Tecnologías y dependencias

- Runtime
- Desarrollo
- Versiones críticas
- Propósito de cada dependencia clave

## 6) Arquitectura de la aplicación

- Patrón general
- Módulos principales
- Flujo de datos
- Decisiones técnicas visibles

## 7) CI/CD (si aplica)

- Pipelines detectados
- Configuración de despliegue
- Automatizaciones visibles
- Si no aplica o no se detecta, indicarlo explícitamente

## Estilo de redacción

- Lenguaje claro y técnico, pero entendible por audiencia mixta.
- Frases concretas, orientadas a decisión.
- No usar relleno ni resumen reducido.
- Si falta información, declararlo en la sección correspondiente.
- Para mejor lectura en PDF: usar tablas compactas, listas cortas y títulos de sección consistentes.

## Criterios de éxito

✅ Se respeta siempre la estructura completa de 7 secciones
✅ Se distinguen ramas principales y secundarias
✅ No se marca `main` u otra rama principal como obsoleta
✅ Se incluyen stack y dependencias con versión y propósito
✅ Se documenta CI/CD o se declara su ausencia

## Recursos

- [patterns.md](patterns.md): criterios de clasificación y redacción
- [examples.md](examples.md): ejemplos de uso
- [template.md](template.md): plantilla base del reporte
