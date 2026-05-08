# claude-skills

Colección de skills personalizados para [Claude Code](https://claude.ai/code).

Cada skill extiende las capacidades de Claude Code con comportamientos específicos que se activan por comando (`/skill-name`) o por frases naturales.

---

## Skills disponibles

| Skill | Categoría | Comando | Descripción |
|-------|-----------|---------|-------------|
| [skills](skills/skills/) | Meta | `/skills` | Lista todos tus skills instalados agrupados por categoría; también guía a Claude a identificar y usar skills relevantes al ejecutar tareas |
| [memory](skills/memory/) | Productividad | `/memory save` / `/memory load` | Guarda y restaura el contexto de una sesión para no perder el progreso |
| [humanizer](skills/humanizer/) | Escritura | `/humanizer` | Elimina patrones de escritura generada por IA para que el texto suene natural y humano |
| [token-optimizer](skills/token-optimizer/) | Dev Tools | `/token-optimizer` | Audita y optimiza el uso de contexto en Claude Code; recupera entre 5–25% del context window |
| [skill-creator](skills/skill-creator/) | Meta | `/skill-creator` | Crea, mejora y evalúa skills; incluye loop de evals, benchmarks y optimización de descripción |
| [ui-ux-pro-max](skills/ui-ux-pro-max/) | Diseño | `/ui-ux-pro-max` | Inteligencia de diseño UI/UX: 67 estilos, 96 paletas, 57 pairings, 13 stacks (React, Next.js, Tailwind, etc.) |

---

## ¿Cómo instalar un skill?

Copia la carpeta del skill dentro de `~/.claude/skills/`:

```bash
# Mac/Linux
cp -r skills/<nombre-del-skill> ~/.claude/skills/

# Windows (PowerShell)
Copy-Item -Recurse skills\<nombre-del-skill> $env:USERPROFILE\.claude\skills\
```

Luego reinicia Claude Code o abre una nueva conversación. El skill estará disponible automáticamente.

---

## Estructura del repo

```
claude-skills/
└── skills/
    └── nombre-del-skill/
        ├── SKILL.md      ← instrucciones que Claude lee al activarse
        └── README.md     ← documentación para humanos
```

---

## Contribuir

Si quieres agregar tu propio skill, abre un PR con:
- La carpeta del skill en `skills/<nombre>/`
- Un `SKILL.md` con el frontmatter `name` y `description`
- Un `README.md` siguiendo el formato de los existentes
