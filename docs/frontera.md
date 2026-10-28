## Parte B

### 1. Respuestas del agente

#### Archivos `CLAUDE.md` cargados al iniciar la sesión

- `blog/CLAUDE.md`
- `blog/blog-api/CLAUDE.md`

#### Skills disponibles

- **Del proyecto:** `marcador-blog-api` y `marcador-blog-ai`, que informan de los cambios registrados por el hook de marcadores de cada repositorio.

#### Nombre del campo

Lo llamé `fragmentos_coincidentes`:

- **En español:** la regla de `blog-ai/CLAUDE.md` lo exige, y este esquema forma parte del OpenAPI público que consume `blog-api`.
- **Sigue el estilo del archivo:** usa `snake_case` y el mismo vocabulario que ya aparece, como `fragmento`, `fragmentos` y `fragmentos_indexados`. "Coincidentes" describe justo lo pedido: los fragmentos del artículo que coincidieron con la búsqueda.
- **No rompe el contrato:** el docstring advierte de que cambiar campos rompe a `blog-api`. Le di valor por defecto `1` para que añadirlo no rompa nada, y `ge=1` porque si un artículo aparece en los resultados, al menos un fragmento suyo ha coincidido.

### 2. Marcadores

`MARCADORES-blog-api.txt` registró el `Edit` de `blog-ai/app/esquemas.py`; `MARCADORES-blog-ai.txt` no existe.