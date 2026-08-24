# Presentaciones de Ingeniería de Software Moderna

## Alcance del repositorio

Este repositorio contiene las presentaciones de la primera mitad del curso Ingeniería de Software Moderna (ISM). Cada carpeta principal tiene un `index.html` generado desde un markdown de Obsidian mediante Advanced Slides.

Los markdowns fuente no están dentro de este repositorio. Se encuentran en el vault de Obsidian, bajo `Diapositivas/Primera mitad/`, organizados por semana y clase. La correspondencia actual es:

| Markdown fuente | Salida publicada |
| --- | --- |
| `Primera mitad/S1/S1 - C1 - Bienvenida al curso y reglas de juego.md` | `bienvenida/index.html` |
| `Primera mitad/S1/S1 - C2 - El proyecto.md` | `proyecto/index.html` |
| `Primera mitad/S2/S2 - C1 - HTML, CSS y Bootstrap.md` | `html-css-bootstrap/index.html` |
| `Primera mitad/S2/S2 - C2 - TypeScript.md` | `typescript/index.html` |

El markdown fuente es la referencia para el contenido. Una edición manual del HTML se perderá cuando se vuelva a exportar desde Obsidian.

## Contenido de las clases

### S1 C1: bienvenida y reglas de juego

`bienvenida/index.html` presenta el curso, la construcción de comunidad y la logística. Incluye las reglas de asistencia y comunicación, la evaluación, el trabajo en grupos, la recolección de usuarios de GitHub, la política de uso de IA y las primeras tareas.

Puntos del curso que aparecen en esta clase:

- La asistencia es obligatoria y exige al menos 80%.
- Las inasistencias justificadas se reportan dentro de los tres días calendario siguientes.
- La mayoría de las entregas se hace por GitHub.
- El proyecto combina trabajo individual y grupal. Cada estudiante desarrolla el front y el back de un módulo funcional.
- El uso de IA está permitido con restricciones. El trabajo manual de clase precede al uso de modelos, y las conversaciones o prompts pueden formar parte de los entregables.
- Algunas entregas pueden requerir sustentación oral.

### S1 C2: el proyecto

`proyecto/index.html` explica cómo leer el enunciado y convertirlo en un diseño inicial del sistema. La clase cubre la creación de repositorios individuales y grupales en Classroom50, la identificación de entidades, atributos, relaciones y reglas de negocio, y el registro de supuestos cuando el enunciado es ambiguo.

También introduce el prototipado de una interfaz estática con HTML y Bootstrap, la separación del sistema en módulos funcionales, los diagramas de dominio y de vista funcional, y la validación de los avances con el profesor. Las tareas incluyen un GIST público, la wiki del repositorio, los diagramas y las historias de usuario.

### S2 C1: HTML, CSS y Bootstrap

`html-css-bootstrap/index.html` introduce la historia breve de la Web y las responsabilidades de HTML, CSS y JavaScript.

- HTML aporta la estructura, la semántica y el DOM.
- CSS define la apariencia de los elementos HTML.
- JavaScript agrega interacción, modifica el DOM y puede consumir APIs.
- Bootstrap ofrece clases y componentes reutilizables, además de una grilla de 12 columnas adaptable a distintos tamaños de pantalla.

La clase termina con documentación de Bootstrap y un bono para crear un sitio sobre un interés personal o un portafolio usando un GIST de referencia.

### S2 C2: TypeScript

`typescript/index.html` parte de los problemas de tipado dinámico de JavaScript y presenta TypeScript como una capa de verificación previa a la ejecución. Explica que el navegador ejecuta JavaScript y que `tsc` revisa el código TypeScript y genera el archivo `.js`.

Los ejemplos cubren tipos básicos, inferencia, funciones, objetos e interfaces, propiedades opcionales, uniones, estrechamiento con `typeof`, condicionales, ciclos, `forEach`, funciones flecha y `map`. La práctica conecta TypeScript con una página HTML, Bootstrap, un arreglo alojado en un GIST, `script.ts`, `tsconfig.json`, `tsc` y Live Server.

## Organización de cada presentación

Cada una de las cuatro carpetas contiene:

- `index.html`, que contiene las diapositivas dentro de plantillas `data-markdown` y arranca Reveal.js.
- `css/`, con `layout.css`, `mattropolis.css` y `vs2015.css`.
- `dist/`, con Reveal.js, temas, fuentes y Font Awesome.
- `plugin/`, con los plugins de Reveal.js usados por la exportación.
- Las imágenes específicas de esa clase, junto a `index.html`.

Los directorios `dist/` y `plugin/` son copias locales del runtime de Reveal.js y de sus plugins. Se repiten en cada presentación para que cada HTML pueda abrirse de forma autónoma. No son el contenido académico del curso.

## Convenciones de autoría

En los markdowns fuente:

- El frontmatter actual usa `bg: "#2E3440"` y `highlightTheme: monokai`.
- `---` separa las diapositivas.
- El primer `#` identifica el título de la presentación y los `##` suelen identificar títulos de diapositivas.
- Se usan bloques de código para ejemplos de HTML, JavaScript, TypeScript, shell y JSON.
- Se usan diagramas Mermaid y enlaces Markdown.
- Las imágenes se insertan con wikilinks de Obsidian, por ejemplo `![[nombre.png]]`. La exportación las convierte en referencias locales como `imagen.png`.
- Algunas diapositivas usan HTML embebido y estilos inline para ajustar el tamaño del contenido. Hay que revisar esas diapositivas después de cualquier cambio.

En el HTML generado se conserva la estructura esperada por Advanced Slides:

- Reveal.js usa un lienzo de 960 por 700 píxeles.
- El tema cargado es `dist/theme/black.css`, con `plugin/highlight/monokai.css` para código.
- La transición actual es `slide`, con controles, progreso e historial activados.
- Se cargan Markdown, resaltado de sintaxis, zoom, notas, MathJax 3, Mermaid, Chart, Custom Controls y Reveal Pointer.
- Las rutas a CSS, JavaScript e imágenes son relativas a la carpeta de cada presentación. Si se mueve un archivo, hay que actualizar el markdown fuente o la ruta generada.

## Flujo de trabajo

1. Editar primero el markdown fuente en Obsidian.
2. Exportar o actualizar la presentación con Advanced Slides.
3. Confirmar que el `index.html` correspondiente y las imágenes locales se actualizaron.
4. Abrir la presentación en un navegador y revisar especialmente imágenes, diagramas Mermaid, bloques de código, diapositivas con HTML inline y posibles desbordamientos.
5. Ejecutar `git diff --check` antes de entregar cambios.

No hay un script de build o de pruebas del curso en la raíz. La validación principal es la exportación desde Obsidian y una revisión visual de los cuatro HTML.

## Texto y documentación

El material está escrito principalmente en español. Conserva en inglés los nombres de APIs, etiquetas HTML, comandos, tipos y mensajes de error que aparecen en el código.

Al escribir o revisar prosa para este proyecto, aplica la skill `unslop` instalada desde `cursor/plugins` en la ruta `pstack/skills/unslop`. Mantén el significado y el tono docente, usa palabras concretas, evita frases promocionales y relleno, y prefiere oraciones cortas con voz activa. No cambies nombres de archivos, URLs, comandos ni bloques de código al limpiar la redacción.

