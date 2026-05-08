# memory

Skill para guardar y restaurar el contexto de una sesión de Claude Code. Al final de una sesión guarda un resumen compacto en `.claude-memory.md` en la raíz del proyecto. Al inicio de una nueva sesión lo lee y te pone al día para continuar sin perder el hilo.

## Instalación

```bash
# Mac/Linux
cp -r skills/memory ~/.claude/skills/

# Windows (PowerShell)
Copy-Item -Recurse skills\memory $env:USERPROFILE\.claude\skills\
```

## Uso

| Comando | Qué hace |
|---------|----------|
| `/memory save` | Guarda el resumen de la sesión actual en `.claude-memory.md` |
| `/memory load` | Lee el archivo y presenta un briefing para reanudar el trabajo |

También puedes activarlo con frases como: *"guarda el progreso"*, *"carga la memoria"*, *"load memory"*, *"save session"*.

## Ejemplo de output

**`/memory save`** genera una entrada como esta:

```markdown
---
## 2026-05-07 | in-progress
**Goal:** Agregar dark mode al navbar del portfolio
**Decisions:**
- localStorage sobre cookies (app estática, sin backend)
**Files:** `app/layout.tsx` (ThemeProvider), `components/Navbar.tsx` (+toggle)
**Errors:** Hydration mismatch → resuelto con suppressHydrationWarning
**Next:**
- [ ] Crear ThemeProvider
- [ ] Escribir tests del toggle
```

**`/memory load`** presenta un briefing estructurado y pregunta por dónde continuar.
