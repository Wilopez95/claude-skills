# Skill: `/skills`

Muestra el listado completo de todos tus skills instalados en Claude Code, con una descripción en español de qué hace cada uno y cómo usarlo.

---

## ¿Qué hace?

Cuando escribes `/skills`, Claude lee automáticamente todos los archivos `SKILL.md` de tu carpeta `~/.claude/skills/` y genera un listado organizado con:

- Nombre del skill y su comando
- Descripción en español de qué hace
- Ejemplo de cómo activarlo (por comando o frase natural)

El listado siempre está actualizado — no requiere mantenimiento manual porque se genera dinámicamente.

---

## Cómo instalarlo

1. Copia la carpeta `skills/` dentro de `~/.claude/skills/`:

```bash
# En Mac/Linux
cp -r skills/skills ~/.claude/skills/skills

# En Windows (PowerShell)
Copy-Item -Recurse skills\skills $env:USERPROFILE\.claude\skills\skills
```

2. Reinicia Claude Code (o abre una nueva conversación).

3. Escribe `/skills` para probarlo.

---

## Cómo usarlo

| Acción | Qué escribir |
|--------|-------------|
| Ver todos los skills | `/skills` |
| Activación por frase | "qué skills tengo", "qué comandos puedo usar", "qué puedo hacer" |

---

## Ejemplo de salida

```
## Tus Skills Disponibles

### /caveman
**Qué hace:** Activa un modo de comunicación ultra-comprimida que reduce el uso de tokens hasta un 75%.
**Cómo usarlo:** Escribe `/caveman` o di "less tokens"

---

### /humanizer
**Qué hace:** Elimina señales de escritura generada por IA, haciendo el texto más natural y humano.
**Cómo usarlo:** Selecciona el texto y di "humanize this"

---
```

---

## Notas

- El skill se omite a sí mismo del listado para no crear ruido.
- Los skills instalados como symlinks también aparecen (se detectan desde el contexto del sistema).
- Nombres de comandos y rutas permanecen en inglés; solo las descripciones van en español.
