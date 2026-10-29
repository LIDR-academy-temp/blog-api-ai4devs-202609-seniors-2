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

**Modelo:** Opus 1M xHigh
**Herramienta:** Claude Code

```
 crea Un CLAUDE.md en la raíz con una sola regla propia del repositorio. En blog-api: este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique. En blog-ai: los nombres de los campos del contrato público deben escribirse en español, nunca en inglés. Las reglas son distintas para poder reconocer después cuál se aplicó.

Un hook que se ejecute al escribir o editar un archivo, mediante PostToolUse para las herramientas Write y Edit. Debe añadir una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Pide que use rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio.

Una skill sencilla llamada marcador-<nombre-del-repo>, cuya descripción indique a qué repositorio pertenece.


Crea un  CLAUDE.md con la siguiente regla: todo archivo nuevo debe empezar con un comentario que lo indique. tambien crea una  CLAUDE.md en  log-ai con la siguente Regla : Los nombres de los campos del contrato público deben escribirse en español, nunca en inglés. Las reglas son distintas para poder reconocer después cuál se aplicó.

en ambos repositorios tambien crea :
Un hook que se ejecute al escribir o editar un archivo, mediante PostToolUse para las herramientas Write y Edit. Debe añadir una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Pide que use rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio.

Una skill sencilla llamada marcador-<nombre-del-repo>, cuya descripción indique a qué repositorio pertenece.
```

**Qué salió:** (opcional, una línea) funcionó a la primera / tuve que insistir / me inventó una ruta que no existe.


## propmt 2
 añade a la clase ResultadoBusqueda, en ../blog-ai/app/esquemas.py, un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda. solo modifica ese archivo y utiliza la herramienta de edición de archivos, nunca un script.

 **Qué salió:**
 Se cargaron dos archivos CLAUDE.md:

1. /usr/local/gerardo/Projects/blog/CLAUDE.md, el de la carpeta que contiene los repositorios. Contiene la sección "REGLA-PADRE":
▎ Este archivo no vive dentro de ningún repositorio: está en la carpeta que los contiene. Por eso, toda respuesta que des aquí termina con esta línea, sola y literal: REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios.
2. /usr/local/gerardo/Projects/blog/blog-api/CLAUDE.md, el del repositorio blog-api. Contiene la sección "Reglas de blog-api":
class RespuestaBuscar(BaseMo

He añadido fragmentos_coincidentes: int = Field(default=1, ge=1) a ResultadoBusqueda en ../blog-ai/app/esquemas.py. Solo he tocado ese archivo, con la herramienta de edición.

- Valor por defecto: he puesto 1 pornos por un fragmento. Así el códigoactual que construye ResultadoBusqueda sigue funcionando sin cambios.
- Falta rellenarlo: el campo valdrá  de búsqueda cuente de verdad losfragmentos por artículo. Eso no está hecho.
- Contrato: esquemas.py dice que est blog-api, y el campo nuevo cambiacontrato/openapi.json. No he regenerado ese archivo porque pediste tocar solo uno.

REGLA-PADRE aplicada: gobierno desdeios.

✻ Cooked for 10s · done 4:02 PM

## propmt 3 

Qué archivos CLAUDE.md se cargaron ala regla de cada uno.

 **Qué salió:**
 Se cargaron dos archivos CLAUDE.md:

1. /usr/local/gerardo/Projects/blog/ue contiene los repositorios. Contiene la sección "REGLA-PADRE":
▎ Este archivo no vive dentro de ningún repositorio: está en la carpeta que los contiene. Por eso, toda respuesta que des aquí termina con eGLA-PADRE aplicada: gobierno desdefuera de todos los repositorios.
2. /usr/local/gerardo/Projects/blog/blog-api/CLAUDE.md, el del repositorio blog-api. Contiene la sección "Reglas de blog-api":
▎ Todo archivo nuevo debe empezar coe.

La segunda regla no se activó en la difiqué un archivo existente y no creé ninguno.

REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios.

## propmt 4
Qué skills tiene disponibles

 **Qué salió:**
Estas son las skills disponibles, agrupadas por tema.

Del espacio de trabajo
- marcador-blog-api: indica que la sesión se abrió en blog-api y dónde se registran los cambios (MARCADORES-blog-api.txt).
- marcador-blog-ai: lo mismo para blog-ai (MARCADORES-blog-ai.txt).

Código y revisión
- code-review: revisa el diff, un PR o una rama, con niveles de esfuerzo y opciones --comment y --fix.
- simplify: limpia el código cambiado (reutilización, simplificación, eficiencia) y aplica los arreglos.
- security-review: revisión de seguridad de los cambios pendientes de la rama.
- run: lanza la aplicación del proyecto para ver un cambio funcionando.
- init: crea un CLAUDE.md con la documentación del código.
- claude-api: referencia de la API de Claude y el SDK de Anthropic.

Configuración y automatización
- update-config: configura el harness mediante settings.json (hooks, permisos, variables de entorno).
- fewer-permission-prompts: añade una lista de permitidos para reducir los avisos de permisos.
- keybindings-help: personaliza atajos de teclado.
- loop: ejecuta un prompt a intervalos recurrentes.
- schedule: crea y gestiona agentes programados en la nube.
- plugin-authoring: crea mods (paneles, barra de estado, comandos, hooks).

Artefactos y visualización
- artifact-design, artifact-diagramming y artifact-capabilities: diseño, diagramas y capacidades de runtime para artefactos.
- dataviz: gráficos, dashboards y visualización de datos.

Navegador y escritorio
- claude-in-chrome, anthropic-skills:chrome-browser, anthropic-skills:built-in-browser y anthropic-skills:computer-use: automatización del navegador y del escritorio.

Documentos y otros formatos
- anthropic-skills:docs, anthropic-skills:docx, anthropic-skills:pdf, anthropic-skills:pptx, anthropic-skills:xlsx y anthropic-skills:google-workspace.

Varias
- anthropic-skills:deep-research: investigación con varias fuentes y un informe final.
- anthropic-skills:skill-creator: crea y mejora skills.
- anthropic-skills:import-memory: importa memoria de otro asistente.
- anthropic-skills:morning: genera el resumen matutino.

REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios.


## propmt 5
 Qué nombre le has dado  al campo y por qué?	

 **Qué salió:**
 Lo llamé fragmentos_coincidentes, por estas razones:

- Sigue el idioma y el estilo del archivo. Los demás campos están en español y en snake_case (post_id, motivos_omision, modelo_embeddings), y los comentarios no llevan tildes.
- Reutiliza el vocabulario existente. RespuestaIndexar ya usa fragmentos para contar los trozos en que se divide un artículo, así que "fragmentos" es el término del dominio.
- Evita confundirse con fragmento. El campo fragmento: str ya existe en ResultadoBusqueda y es el texto del mejor fragmento. Con el nombre en plural y el sufijo _coincidentes queda claro que el nuevo es un conteo y no otro texto.
- Refleja lo que pediste. Pediste cuántos fragmentos "han coincidido con la búsqueda", y "coincidentes" recoge ese verbo.

No comparé alternativas por escrito. Elegí este nombre por lo anterior, y renombrarlo es trivial si prefieres otro, por ejemplo num_fragmentos. Como el campo forma parte del contrato con blog-api, conviene fijar el nombre antes de que blog-api lo consuma.

REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios.