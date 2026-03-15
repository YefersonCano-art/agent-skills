# Agent Skills

Repositorio de skills para agentes (Copilot/CLI), con versiones en español e inglés según el caso.

## Convención de este repositorio

Cada skill vive en su propia carpeta y normalmente incluye:

- `SKILL.md`: comportamiento, activación, límites y formato de salida.
- `SKILL.json` (opcional pero recomendado): metadata ligera (`name`, `id`, `description`, referencias).
- Archivos de apoyo según necesidad: `patterns.md`, `examples.md`, `template.md`.

Estructura observada en este repo:

- `profesor-programacion/` → skill pedagógico (modo profesor).
- `programming-professor/` → English version of the pedagogical professor mode skill.
- `reporte-repositorio/` → skill en español para reporte ejecutivo-técnico.
- `repository-report/` → skill en inglés equivalente al anterior.

---

## Skills disponibles

### 🧠 profesor-programacion

Modo profesor activado por palabras clave como **"profe"** o **"profesor"**. Prioriza enseñanza guiada y evita modificar archivos del proyecto.

- Carpeta: `profesor-programacion/`
- ID sugerido: `profesor-programacion`
- Instalación:

```bash
npx skills add https://github.com/YefersonCano-art/agent-skills --skill profesor-programacion
```

---

### 🧑‍🏫 programming-professor

English version of the professor skill. Activates with keywords like **"prof"** or **"professor"** and prioritizes guided teaching without directly modifying project files.

- Carpeta: `programming-professor/`
- ID: `programming-professor`
- Install:

```bash
npx skills add https://github.com/YefersonCano-art/agent-skills --skill programming-professor
```

---

### 📊 reporte-repositorio

Genera un **Reporte Ejecutivo-Técnico** de repositorio en 7 secciones, solo ante solicitud explícita.

- Carpeta: `reporte-repositorio/`
- ID: `reporte-repositorio`
- Instalación:

```bash
npx skills add https://github.com/YefersonCano-art/agent-skills --skill reporte-repositorio
```

---

### 📈 repository-report

Versión en inglés del reporte ejecutivo-técnico con estructura fija de 7 secciones.

- Carpeta: `repository-report/`
- ID: `repository-report`
- Instalación:

```bash
npx skills add https://github.com/YefersonCano-art/agent-skills --skill repository-report
```

---
