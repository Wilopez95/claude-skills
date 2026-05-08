---
name: skills
description: Muestra el listado completo de skills disponibles con descripción en español de cómo usarlos. Úsalo cuando el usuario escriba /skills, pregunte qué comandos tiene disponibles, qué skills hay instalados, o cómo usar alguna funcionalidad de Claude Code. También actívalo si el usuario pregunta "qué puedo hacer", "qué comandos tienes", o similar.
---

# Skills — Listado de Habilidades

Cuando este skill se activa, muestra al usuario todos sus skills disponibles con descripciones en español.

## Cómo proceder

1. Lee todos los archivos `C:\Users\wilop\.claude\skills\*\SKILL.md` usando Glob + Read
2. Para cada skill, extrae el campo `name` y `description` del frontmatter YAML
3. Presenta el listado completo en el formato de abajo
4. Los nombres de comandos y rutas permanecen en inglés; solo las explicaciones van en español
5. Omite este mismo skill (`skills`) del listado

Si un skill tiene una descripción larga en inglés, resúmela en 1-2 líneas en español — no la traduzcas literalmente palabra por palabra.

## Formato de salida

```
## Tus Skills Disponibles

### /nombre-del-skill
**Qué hace:** descripción breve en español
**Cómo usarlo:** escribe `/nombre-del-skill` o di algo como "frase de ejemplo que lo activa"

---
```

Ordena los skills agrupando primero los relacionados (todos los `caveman-*` juntos, por ejemplo), luego el resto en orden alfabético.

Al final del listado, agrega una nota:

> 💡 Este listado se genera leyendo los archivos SKILL.md instalados en `~/.claude/skills/`, por lo que siempre refleja tus skills actuales.
