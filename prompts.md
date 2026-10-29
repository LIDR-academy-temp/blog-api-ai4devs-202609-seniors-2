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

Borra el ejemplo de abajo cuando escribas el primero.

---

## Prompt 1

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
Resumen el proyecto
```

**Qué salió:** Funcionó a la primera: resumen del sistema de tres repos, la estructura de blog-api y el ejercicio de la frontera.

## Prompt 2

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
Ahora vamos a crear un CLAUDE.md en la raiz de cada respositorio indicado. Uno para este repositorio indicando una regla: este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique. Luego siguendo lo mismo, crea un CLAUDE.md en blog-ai, es otra aplicacion que se encuentra al mismo nivel que esta en la carpeta blogs. Este archivo debe incluir la siguiente regla: los nombres de los campos del contrato público deben escribirse en español, nunca en inglés.
```

**Qué salió:** Creó los dos CLAUDE.md; añadió por su cuenta exenciones a la regla de blog-ai (errores de FastAPI, id/slug/post_id) y detectó el CLAUDE.md de la carpeta padre con la REGLA-PADRE.

## Prompt 3

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
Ahora vamos a crear un hook que se ejecute al escribir o editar un archivo, mediante PostToolUse para las herramientas Write y Edit. Debe añadir una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Pide que use rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio.
```

**Qué salió:** Funcionó: hook en .claude/settings.json de cada repo; al editar blog-ai/CLAUDE.md desde blog-api solo se disparó el hook de blog-api y no se creó MARCADORES-blog-ai.txt.

## Prompt 4

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
Finalmente vas a crear una skill sencilla llamada marcador-<nombre-del-repo>, cuya descripción indique a qué repositorio pertenece.
```

**Qué salió:** Creó marcador-blog-api y marcador-blog-ai; en esta sesión (abierta desde blog-api) solo apareció disponible marcador-blog-api.

## Prompt 5

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
/registrar-prompts
```

**Qué salió:** Volcó los prompts de la sesión a prompts.md y borró el ejemplo de la plantilla.

## Prompt 6

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
Como desarrollador, vas a añadir a la clase ResultadoBusqueda, en ../blog-ai/app/esquemas.py, un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda. Es importante que debas modificar solo ese archivo y utilizar la herramienta de edición de archivos, nunca un script.

Al terminar, responde por separado:

1.Qué archivos CLAUDE.md se cargaron al iniciar la sesión, citando la regla de cada uno.

2.Qué skills tiene disponibles.

3.Qué nombre ha dado al campo y por qué.
```

**Qué salió:** Añadió `fragmentos_coincidentes: int = Field(default=1, ge=1)` con Edit, solo en ese archivo, y contestó las tres preguntas (CLAUDE.md de la carpeta padre y de blog-api; ninguno de blog-ai). No calculó el valor real en la búsqueda ni regeneró `contrato/openapi.json`, y después el cambio desapareció del archivo en disco.

## Prompt 7

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
/registrar-prompts
```

**Qué salió:** Interrumpido por la persona antes de escribir nada en prompts.md.

## Prompt 8

**Modelo:** Opus 5.5 (claude-opus-5-5)
**Herramienta:** Claude Code (CLI)

```
/registrar-prompts
```

**Qué salió:** Relanzado tras la interrupción; registró los prompts 6 a 8.
