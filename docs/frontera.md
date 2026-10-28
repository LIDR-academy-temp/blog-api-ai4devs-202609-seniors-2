# Frontera

1. El agente dijo haber cargado el CLAUDE.md global, el de `blog/` (REGLA-PADRE) y el de `blog-api` (comentario de dueño del contenido); no cargó el de `blog-ai`. Skills de proyecto: `marcador-blog-api` y `marcador-blog-ai`. Nombró el campo `fragmentos_coincidentes` (español/snake_case, alineado al contrato de blog-ai aunque no citara su CLAUDE.md).

2. `MARCADORES-blog-api.txt` registró el `Edit` de `blog-ai/app/esquemas.py` (ruta absoluta); `MARCADORES-blog-ai.txt` no existe. El hook que se ejecuta es el del cwd de la sesión (`blog-api`), no el del repo donde vive el archivo tocado.
