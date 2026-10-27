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

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
Crea `CLAUDE.md` en la raiz de este proyecto `blog-api` para indicar que es el dueño del contenido,
debe tener las regla: todo archivo nuevo debe empezar con un comentario que indique que `blog-api` es el dueño del contenido. En el proyecto de `blog-ai` que esta al lado indica en su  `CLAUDE.md` los nombres de los campos del contrato público deben escribirse en español, nunca en inglés.
```

**Qué salió:** funcionó a la primera; creó los dos `CLAUDE.md` (en `blog-ai` no existía).

## Prompt 2

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
no todavia, crea en los dos proyectos tambien un hook Crea un hook, ejecutado tras editar archivo con `PosToolUse` para herramientas [Write, Edit] Debe añadir una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Pide que use rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio.
```

**Qué salió:** funcionó a la primera; creó `.claude/settings.json` y `.claude/hooks/marcador.sh` en los dos repos, probado a mano.

## Prompt 3

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
crea ahora en los dos proyectos una skill Una skill sencilla llamada marcador-<nombre-del-repo>, cuya descripción indique a qué repositorio pertenece.
```

**Qué salió:** funcionó a la primera; la skill lee y resume el `MARCADORES-<repo>.txt` del hook.

## Prompt 4

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
guarda los prompts de esta sesion en @prompts.md como se indica estoy effor medium y contexto 1.0M
```

## Prompt 5

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
Añade a la clase `ResultadoBusqueda` en @../blog-ai/app/esquemas.py un campo que indique cuántos fragmentos del artículo han coincidido en la búsqueda. Restricción: solo modificar ese archivo y usa la herramienta de edición de archivos, nunca un script
```

**Qué salió:** funcionó a la primera; añadió `fragmentos_coincidentes: int = Field(default=1, ge=1)` solo en ese archivo, con la herramienta Edit. Avisó de que la búsqueda todavía no rellena el campo y de que hay que regenerar `contrato/openapi.json`.

## Prompt 6

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
Qué archivos CLAUDE.md se cargaron al iniciar la sesión, cita la regla de cada uno.
```

**Qué salió:** citó `blog/CLAUDE.md` (REGLA-PADRE) y `blog/blog-api/CLAUDE.md` (comentario de dueño en archivos nuevos). Señaló que el `CLAUDE.md` de `blog-ai` no se había cargado.

## Prompt 7

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
Qué skills tiene disponibles.
```

**Qué salió:** listó todas las skills disponibles, entre ellas `marcador-blog-api` y `marcador-blog-ai`.

## Prompt 8

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
Qué nombre ha dado al campo de la clase  y por qué.
```

**Qué salió:** `fragmentos_coincidentes`, porque sigue el estilo del archivo, no se confunde con `fragmento` ni con `fragmentos`, y el nombre forma parte del contrato público.

## Prompt 9

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
Crea un archivo `docs/frontera.md` con una "Parte B: las dos frases"

1. *Qué dijo el agente en el paso 4*: qué archivos CLAUDE.md dijo haber cargado, qué skills tenía disponibles y qué nombre dio al campo.
El agente dijo haber cargado   `blog/CLAUDE.md` y `blog/blog-api/CLAUDE.md`, skill tenia `marcardor-blog-api`y `marcador-blog-ai` y luego el campo le puso  `ragmentos_coincidentes`

2. *Qué encontraste en cada archivo de marcadores y qué indica sobre dónde se ejecuta cada guardarraíl.*
Pues realmente solo se creo el de blog-api el hook solo se ejecuta el de blog-api `blog-api/MARCADORES-blog-api.txt` aunque el contenido es el registro de la edición de "2026-10-27T19:34:13+01:00       Edit    /home/manu/blog/blog-ai/app/esquemas.py"
```

**Qué salió:** funcionó a la primera; creó `docs/frontera.md` con la cabecera de dueño de blog-api y corrigió las erratas.

## Prompt 10

**Modelo:** Opus 1M Medium
**Herramienta:** Claude Code

```
añade los comentarios de la sesion a @prompts.md recuerda el modelo usado es con effort medium 1.0M
```
