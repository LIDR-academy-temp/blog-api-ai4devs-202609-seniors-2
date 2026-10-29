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

**Modelo:** Sonnet 5.5 Medium
**Herramienta:** Claude Code

```
 Necesito que crees lo siguiente tanto en blog-api, como blog-ai:

* Crea el hook y la skill dentro de la carpeta .claude de cada repositorio.
* Un CLAUDE.md en la raíz con una sola regla propia del repositorio. En blog-api: este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique. En blog-ai: los nombres de los campos del contrato público deben escribirse en español, nunca en inglés.
* Un hook que se ejecute al escribir o editar un archivo, mediante PostToolUse para las herramientas Write y Edit. Debe añadir una línea a MARCADORES-blog-api.txt y MARCADORES-blog-ai.txt respectivamente en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Usa rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio.
* Una skill sencilla llamada marcador-blog-api y otra marcador-blog-ai cuya descripción indique a qué repositorio pertenece. 

La ruta de blog-ai esta en ../blog-ai.
Finalmente, no cambies nada mas ni mejores, solo haz lo que se te pidió.
```

**Qué salió:** Funcionó a la primera creo los archivos que se le pidio y no modifico nada mas.

## Prompt 2

**Modelo:** Sonnet 5.5 Medium
**Herramienta:** Claude Code

```
Necesito que añadas a la clase ResultadoBusqueda, en ../blog-ai/app/esquemas.py, un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda.

Solo debes modificar ese archivo y utilizar la herramienta de edición de archivos, nunca un script.

Al finalizar, responde lo siguiente por separado:
Qué archivos CLAUDE.md se cargaron al iniciar la sesión, citando la regla de cada uno.
Qué skills tiene disponibles.
Qué nombre ha dado al campo y por qué.
```

**Qué salió:** Modifico el archivo que se le pidio y creo un MARCADORES-blog-api.txt y MARCADORES-blog-ai.txt no lo creo.
