<!-- Propiedad de blog-api: este repositorio es el dueño de este contenido. -->
## Parte B

### Qué dijo el agente en el paso 4

Cargó dos archivos CLAUDE.md al iniciar:
- El de la carpeta padre: `.../blog/CLAUDE.md` (la REGLA-PADRE)
- El del repo donde arrancó: `.../blog/blog-api/CLAUDE.md`

<br>

De skills de proyecto solo tenía una:
- `marcador-blog-api`: muestra el registro de `MARCADORES-blog-api.txt`.

No apareció ninguna de `blog-ai`. Pasa lo mismo que con su CLAUDE.md: añadir el directorio no carga su `.claude/`. El resto eran skills globales.
<br>

Llamó al campo `fragmentos_coincidentes`. Dijo que lo puso en español por la regla del CLAUDE.md de `blog-ai`, pero eso lo sabía porque leyó el archivo a mano, no porque se hubiera cargado. Además, "fragmentos" ya es como se dice en el resto del esquema (`fragmento`, `fragmentos_indexados`).

### Qué encontré en cada archivo de marcadores y qué indica sobre dónde se ejecuta cada guardarraíl

- `MARCADORES-blog-api.txt` tiene todas las ediciones, incluida la de `blog-ai/app/esquemas.py`. El hook de `blog-api` se dispara con cualquier archivo que toque la sesión, esté en el repo que esté.
- `MARCADORES-blog-ai.txt` no existe. Aquí `blog-ai` ni siquiera tiene `.claude/`, pero igual queda claro que los hooks son de la sesión (el repo desde donde se arranca) y no del repo al que pertenece el archivo.
- Conclusión: los guardarraíles de `blog-api` (hook, skill) mandan en todo lo que hace la sesión, y los de `blog-ai` solo se respetan si el agente los lee por su cuenta.
