# Prompts

Aquí van **todos los prompts que lanzaste** para hacer el ejercicio, en el orden en que los
lanzaste, con el modelo y la herramienta de cada uno.

Esto no es papeleo. Lo que se revisa es **cómo pediste las cosas**, no solo lo que salió: un
resultado flojo con un prompt bueno y un resultado flojo con un prompt vago necesitan feedback
distinto, y sin este archivo no se distinguen.

## Cómo rellenarlo

- Un apartado `## Prompt N` por cada prompt.
- **Pega el prompt tal cual lo lanzaste**, dentro del bloque de código, aunque ocupe diez líneas
  y aunque tenga faltas. No lo reescribas para que quede bien: el que arreglaste mentalmente
  después no es el que lanzaste.
- Incluye también los que **no funcionaron**. Suelen ser los más útiles de leer.
- `Modelo` y `Herramienta` en todos. Si cambiaste de una a otra a mitad, se nota aquí.

---

## Prompt 1

**Modelo:** Opus 5.5 · Claude Pro
**Herramienta:** Claude Code (sesión en blog-api, sin --add-dir)

```
En blog-api y en ../blog-ai crea solo estas tres piezas en cada repo, sin tocar nada más:

1) CLAUDE.md en la raíz con una sola regla propia:
   - blog-api: este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique.
   - blog-ai: los nombres de los campos del contrato público deben escribirse en español, nunca en inglés.

2) Un hook PostToolUse para Write y Edit que añada una línea a MARCADORES-<nombre-del-repo>.txt en la raíz de su propio repo, con fecha, herramienta y ruta del archivo modificado. Usa rutas absolutas (el hook puede registrar cambios fuera de su repo).

3) Una skill sencilla llamada marcador-<nombre-del-repo> cuya descripción indique a qué repositorio pertenece.
```

**Qué salió:** funcionó a la primera; creó CLAUDE.md, hooks `.cjs` + settings.json y skills en ambos repos.

---

## Prompt 2

**Modelo:** Opus 5.5 · Claude Pro
**Herramienta:** Claude Code (`claude --add-dir ../blog-ai` desde blog-api; auto mode on)

```
Añade a la clase ResultadoBusqueda en ../blog-ai/app/esquemas.py un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda.

Modifica solo ese archivo y usa la herramienta de edición de archivos (Edit), nunca un script.

Cuando termines, responde por separado:
1) Qué archivos CLAUDE.md se cargaron al iniciar la sesión, citando la regla de cada uno.
2) Qué skills tienes disponibles.
3) Qué nombre le diste al campo y por qué.
```

**Qué salió:** Edit en esquemas.py con `fragmentos_coincidentes`; respondió las tres preguntas; el marcador quedó solo en blog-api.
