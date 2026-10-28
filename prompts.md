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

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
durante esta sesion vas a apuntar todos los prompts que te envie en el fichero @prompts.md, este incluido. En el propio fichero tienes las instruccuines para rellenarlo
```

**Qué salió:** borra el ejemplo y empieza a apuntar los prompts de la sesión.

## Prompt 2

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Vas a crear tres elementos en 2 repositorios. Los 2 repositos estan en subdirectorios del directorio `blog`, padre del directorio dende estas. Los subdirectorios se llaman:
  - `blog-api`
  - `blog-ai`

Crea un fichero CLAUDE.md una sola regla propia:
 - en `blog-api`: este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique.
 - en `blog-ai` : los nombres de los campos del contrato público deben escribirse en español, nunca en inglés

Crea un hook que se ejecute al escribir o editar un archivo:
Añade una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado.
Utiliza rutas absolutas.

Una Skill con:
  - name: marcador-<nombre-del-repo>
  - description: <nombre-del-repo>
```

**Qué salió:** CLAUDE.md, hook PostToolUse (Write/Edit) y skill marcador-<repo> creados en blog-api y blog-ai.

## Prompt 3

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Añade a la clase ResultadoBusqueda, en ../blog-ai-/app/esquemas.py, un cmapo que indique cuántos fragmentos del artículo han coincidido con la búsqueda.
Modifica solo ese archivo. Utiliza la herramienta de edición de archivos, NUNCA un script.
```

**Qué salió:** Hizo la petición. Sigió la instruccion del CLAUDE.md del directorio padre (blog). En el directorio actual (blog-api) siguió el skil o hook.

## Prompt 4

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Qué archivos CLAUDE.md se cargaron al iniciar la sesión, citan la regla de cada uno.
```

**Qué salió:** dos CLAUDE.md cargados al inicio: el de `blog` (carpeta padre, REGLA-PADRE) y el de `blog-api`. El de `blog-ai` no se cargó.

## Prompt 5

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Qué skills tienes disponibles
```

**Qué salió:** lista de skills agrupadas: las dos del proyecto (`marcador-blog-api`, `marcador-blog-ai`), las del plugin engineering, las integradas de Claude Code y las de anthropic-skills.

## Prompt 6

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Qué nombre le has dado al campo y por qué
```

**Qué salió:** `fragmentos_coincidentes`: en español y con el mismo patrón que `fragmentos_indexados`, por coherencia con el archivo y el contrato; no por la regla del CLAUDE.md de blog-ai, que no se cargó.


