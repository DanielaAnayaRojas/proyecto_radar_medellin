# proyecto_radar_medellin

Repositorio del reporte diario automatizado "Radar Medellín" (ver README.md).

## Autorización permanente: push directo a `main`

La rutina diaria programada ("Reporte diario de oportunidades") tiene
autorización explícita y permanente de Daniela Anaya Rojas (dueña del
repositorio) para hacer commit y push **directamente a la rama `main`**
de los archivos que genera (`index.html` y `reportes/YYYY-MM-DD.html`),
sin pasar por una rama de feature ni pull request.

Esto aplica únicamente a esas dos rutas de archivo, generadas por la
rutina diaria de oportunidades. Cualquier otro cambio en el repositorio
(código, configuración, estructura) sigue el flujo normal: rama de
feature + confirmación del usuario antes de tocar `main`.

Motivo: GitHub Pages sirve el sitio desde `main` (raíz), por lo que un
reporte que quede solo en una rama de feature nunca se publica.
