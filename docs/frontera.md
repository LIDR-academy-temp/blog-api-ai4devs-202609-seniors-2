**Frase 1**

El agente dijo haber cargado al iniciar la sesión el CLAUDE.md de la carpeta blog/ (REGLA-PADRE, que le exige terminar cada respuesta con una línea fija) y el de blog-api (todo archivo nuevo debe empezar con un comentario que indique que el repositorio es dueño del contenido), y afirmó que el de blog-ai no se cargó; dijo tener disponibles, entre muchas otras, las skills marcador-blog-api y marcador-blog-ai, y llamó al campo fragmentos_coincidentes, justificándolo por la convención en español y snake_case del archivo y no por la regla de blog-ai.

**Frase 2**

En MARCADORES-blog-api.txt encontré una línea con la ruta absoluta de un archivo de blog-ai, mientras que MARCADORES-blog-ai.txt no se creó, lo que indica que, al iniciar la sesión desde blog-api, solo se cargó la configuración de ese repositorio y el hook de blog-ai no se ejecutó: Claude Code lee CLAUDE.md, hooks y settings desde la carpeta donde se inicia la sesión (y las que están por encima).