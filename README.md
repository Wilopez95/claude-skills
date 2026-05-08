# claude-skills

Colección de skills personalizados para [Claude Code](https://claude.ai/code).

Cada skill extiende las capacidades de Claude Code con comportamientos específicos que se activan por comando (`/skill-name`) o por frases naturales.

---

## Skills disponibles

| Skill | Comando | Descripción |
|-------|---------|-------------|
| [skills](skills/skills/) | `/skills` | Lista todos tus skills instalados con descripción en español |
| [memory](skills/memory/) | `/memory save` / `/memory load` | Guarda y restaura el contexto de una sesión para no perder el progreso |

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
