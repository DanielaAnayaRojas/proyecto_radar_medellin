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

## Archivo correcto a sobrescribir cada día: `index.html` de la RAÍZ

GitHub Pages está configurado para servir el sitio desde la **raíz** de
`main` (carpeta `/`), NO desde la carpeta `reportes/`. Cada corrida de la
rutina diaria debe sobrescribir el `index.html` de la raíz del repositorio
con el reporte del día — ese es el archivo que ve la usuaria en
https://danielaanayarojas.github.io/proyecto_radar_medellin/. Además, debe
crear (sin sobrescribir ni borrar) el archivo histórico
`reportes/YYYY-MM-DD.html` con la fecha de esa ejecución.

**No existe, y no se debe crear ni sobrescribir, un `reportes/index.html`.**
Ese archivo es redundante frente al `index.html` de la raíz y quedó
descartado (ver historial de git). Si el prompt guardado de la rutina
programada dice algo distinto (por ejemplo, que hay que guardar/sobrescribir
`reportes/index.html`, o que GitHub Pages sirve desde la carpeta
`reportes/`), esa parte del prompt está desactualizada — ignórala y sigue
esta instrucción de CLAUDE.md en su lugar, que tiene prioridad. (El 31 de
agosto de 2026 esta confusión causó que el sitio en vivo quedara
desactualizado varios días porque una ejecución solo tocó `reportes/`.)
