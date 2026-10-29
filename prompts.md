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

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
crea un archivo CLAUDE.md en la raiz de este proyecto que indique que "este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique."
```

**Qué salió:** CLAUDE.md creado

---

## Prompt 2

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
crea un archivo CLAUDE.md en la raiz del proyecto hermano al actual "blog-ai" que indique: "los nombres de los campos del contrato público deben escribirse en español, nunca en inglés."
```

**Qué salió:** CLAUDE.md creado. Dice que este archivo no se cargará en esta sesión porque no hace parte del proyecto

---

## Prompt 3

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
crea un hook mediante PostToolUse para las herramientas Write y Edit de un archivo para cada repositorio blog-api y blog-ai. Que agregue una linea al archivo MARCADORES-<nombre-del-repo>.txt en la raiz de su propio repositorio (ya sea blog-api o blog-ai) con la fecha, la herramienta utilizada y la ruta del archivo modificado. Que use rutas absolutas.
```

**Qué salió:** Ambos hooks creados

---

## Prompt 4

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Crea una skill sencilla llamada marcador-<nombre-del-repo> para cada repositorio blog-api y blog-ai, cuya descripción indique a qué repositorio pertenece.
```

**Qué salió:** Ambas skills creadas

---

## Prompt 5

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Añade a la clase ResultadoBusqueda, en ../blog-ai/app/esquemas.py, un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda.
Solo debes modificar ese archivo y utiliza la herramienta de edición de archivos, nunca un script.
```

**Qué salió:** Cambio realizado

---

## Prompt 6

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Dame la ruta de los archivos CLAUDE.md que cargaste en esta sesión.
```

**Qué salió:** Los tres CLAUDE.md en jerarquia: el del PC, el del directorio padre y el del repo de la sesion actual.

---

## Prompt 7

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Que skills tienes disponible?
```

**Qué salió:** Los de ambos repositorios.

---

## Prompt 8

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Que nombre has dado al nuevo campo y por qué?
```

**Qué salió:** El campo se llama fragmentos_coincidentes. pero no tomando las instrucciones del CLAUDE.md de blog-ai
