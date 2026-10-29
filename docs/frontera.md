<!-- blog-api: dueño del contenido del blog «Corriente». -->

# Frontera entre repositorios — Parte B

La sesión de Claude Code se abrió en `blog-api`, con `blog-ai` añadido como directorio de
trabajo adicional. Desde ahí, en el paso 4, el agente editó un archivo de `blog-ai`
(`app/esquemas.py`).

## 1. Qué dijo el agente en el paso 4

### Archivos CLAUDE.md que dijo haber cargado

| Archivo | Regla que citó |
|---|---|
| `blog/CLAUDE.md` (carpeta padre, fuera de todo repo) | **REGLA-PADRE**: toda respuesta termina con la línea literal «REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios.» |
| `blog/blog-api/CLAUDE.md` | **Cabecera de propiedad del contenido**: todo archivo nuevo del repo empieza con `// blog-api: dueño del contenido del blog «Corriente».`, con la sintaxis de comentario de su tipo. No se aplica a archivos que ya existen ni a JSON. |

Dijo de forma explícita que **no se cargó `blog-ai/CLAUDE.md`**, aunque el archivo que
editaba estaba en `blog-ai`. Por eso no tuvo en contexto la regla de ese repo: «los nombres
de los campos del contrato público deben escribirse en español» y «si añades o cambias un
campo, actualiza `contrato/openapi.json`».

### Skills que dijo tener disponibles

- **Del proyecto:** `registrar-prompts`, `marcador-blog-api` y `marcador-blog-ai`.
- **Generales de Claude Code:** `dataviz`, `artifact-design`, `artifact-diagramming`,
  `artifact-capabilities`, `update-config`, `keybindings-help`, `code-review`, `simplify`,
  `fewer-permission-prompts`, `loop`, `schedule`, `claude-api`, `claude-in-chrome`, `run`,
  `plugin-authoring`, `init` y `security-review`.
- **De `anthropic-skills`:** `artifact-emulator`, `built-in-browser`, `chrome-browser`,
  `computer-use`, `deep-research`, `docs`, `docx`, `google-workspace`, `import-memory`,
  `morning`, `pdf`, `pptx`, `skill-creator` y `xlsx`.

A diferencia de la sesión del prompt 4, en la que solo aparecía `marcador-blog-api`, aquí
aparecieron las dos skills de marcador. Las skills de `blog-ai` sí se descubrieron por estar
en un directorio de trabajo adicional. Su CLAUDE.md y su hook, en cambio, no se cargaron.

### Nombre del campo

`fragmentos_coincidentes: int = Field(default=1, ge=1)`, por estas razones:

- **Vocabulario del archivo:** sigue el de `esquemas.py` (`fragmento`, `fragmentos`,
  `fragmentos_indexados`), en español y en snake_case.
- **Qué cuenta:** `_coincidentes` indica que son los fragmentos que coincidieron con la
  búsqueda, no todos los del post.
- **`default=1` y `ge=1`:** si un post aparece en los resultados, al menos uno de sus
  fragmentos coincidió. El valor por defecto hace el cambio aditivo: no rompe el código que
  ya construye `ResultadoBusqueda`.

El nombre cumple la regla de `blog-ai` («en español»), pero **por imitar el archivo, no
porque el agente la conociera**. La otra mitad de esa regla, actualizar
`contrato/openapi.json`, no se cumplió. El agente solo la mencionó como tarea pendiente,
porque el prompt le prohibía tocar otros archivos.

## 2. Qué hay en cada archivo de marcadores

### `blog-api/MARCADORES-blog-api.txt`

```
2026-10-28T23:05:03-0500	Edit	/Users/chai/Documents/GitHub/blog/blog-ai/CLAUDE.md
2026-10-28T23:05:03-0500	Edit	/Users/chai/Documents/GitHub/blog/blog-ai/CLAUDE.md
2026-10-28T23:16:16-0500	Edit	/Users/chai/Documents/GitHub/blog/blog-ai/app/esquemas.py
2026-10-28T23:22:17-0500	Edit	/Users/chai/Documents/GitHub/blog/blog-api/prompts.md
```

- Tres de las cuatro entradas son **archivos de `blog-ai`**, y el hook que las registró es
  el de `blog-api`.
- La edición de `esquemas.py` del paso 4 (23:16:16) quedó registrada aquí. El campo se
  quitó después del archivo fuera de Claude Code, y eso no dejó marcador: el hook solo ve
  lo que hacen las herramientas `Write`/`Edit` del agente.
- Las dos primeras líneas son idénticas, con la misma marca de tiempo. El registro no
  permite distinguir si fueron dos `Edit` seguidos o un doble disparo.

### `blog-ai/MARCADORES-blog-ai.txt`

**No existe.** El hook de `blog-ai` está bien definido en `blog-ai/.claude/settings.json`
(`PostToolUse`, `Write|Edit`). Aun así, no se disparó nunca, ni siquiera al editar
`blog-ai/CLAUDE.md` y `blog-ai/app/esquemas.py`.

## Qué indica sobre dónde se ejecuta cada guardarraíl

Los guardarraíles los aplica **la sesión que hace el cambio, según dónde se abrió**, no el
repositorio al que pertenece el archivo tocado.

| Guardarraíl | De dónde se carga | ¿Protege `blog-ai` al editar desde `blog-api`? |
|---|---|---|
| `blog/CLAUDE.md` (REGLA-PADRE) | Ancestros del directorio de arranque | Sí: gobierna cualquier sesión abierta dentro de `blog/` |
| `blog-api/CLAUDE.md` | Directorio de arranque | Se aplica, pero es la regla del repo equivocado para ese archivo |
| `blog-ai/CLAUDE.md` | Solo si la sesión arranca en `blog-ai` (o por debajo) | **No**: no se cargó |
| Hook de `blog-api` | `.claude/settings.json` del directorio de arranque | Se dispara con cualquier archivo, esté donde esté (por eso las rutas absolutas) |
| Hook de `blog-ai` | Igual: solo si la sesión arranca en `blog-ai` | **No**: nunca se disparó |
| Skills `marcador-*` | Directorio de arranque y directorios adicionales | Sí: aparecieron las dos |

Conclusión: **un repositorio no puede protegerse a sí mismo de una sesión abierta en otro**.
Las reglas y los hooks de `blog-ai` solo valen cuando se trabaja *desde* `blog-ai`. Lo único
que gobierna a la vez a los dos repos es lo que está por encima de ambos, como
`blog/CLAUDE.md`. Para que el contrato de `blog-ai` se respete de verdad, la comprobación
tiene que vivir donde no dependa de quién abra la sesión, por ejemplo en CI o en un test
sobre `contrato/openapi.json`.
