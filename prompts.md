<!-- Propiedad de blog-api: este repositorio es el dueño de este contenido. -->
# Prompts

## Prompt 1

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
crea un archivo claude.md que indique que este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique
```

**Qué salió:** Lo hizo a la primera, con el comentario según el tipo de archivo.

---

## Prompt 2

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
en el proyecto blog-ai crea un claude.md que especifique que  los nombres de los campos del contrato público deben escribirse en español, nunca en inglés
```

**Qué salió:** Lo hizo bien. Avisó de campos del contrato que siguen en inglés (`slug`, `id`, `detail`…).

---

## Prompt 3

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
crea un hook que debe añadir una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Pide que use rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio
```

**Qué salió:** Lo hizo a la primera y lo probó con archivos de fuera del repo.

---

## Prompt 4

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
crea una skill sencilla llamada marcador-<nombre-del-repo>, cuya descripción indique a qué repositorio pertenece.
```

**Qué salió:** Lo hizo a la primera.


## Prompt 5

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
/add-dir ../blog-ai
```

**Qué salió:** Ya estaba añadido como directorio de trabajo.

---

## Prompt 6

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
añade a la clase ResultadoBusqueda, en ../blog-ai/app/esquemas.py, un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda. debes modificar solo ese archivo y utilizar la herramienta de edición de archivos, nunca un script.
```

**Qué salió:** Funcionó a la primera. Usó Edit y tocó solo ese archivo.

---

## Prompt 7

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Qué archivos CLAUDE.md se cargaron al iniciar la sesión
```

**Qué salió:** Dos: el de `blog/` y el de `blog-api`. El de `blog-ai` no se cargó; lo había leído a mano.

---

## Prompt 8

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Qué skills tiene disponibles.
```

**Qué salió:** Solo una de proyecto, `marcador-blog-api`. Ninguna de `blog-ai`.

---

## Prompt 9

**Modelo:** Opus 5.5
**Herramienta:** Claude Code

```
Qué nombre has dado al campo y por qué?
```

**Qué salió:** `fragmentos_coincidentes`, en español por la regla de `blog-ai`, que conocía porque leyó ese CLAUDE.md a mano.
