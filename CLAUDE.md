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

## Regla estricta de verificación de links (no negociable)

Cada link publicado debe abrir exactamente la página que el reporte describe.
Un link roto o desactualizado NO es aceptable bajo ninguna circunstancia —
esto tiene prioridad sobre "mostrar más oportunidades".

- Antes de incluir cualquier oportunidad, intenta primero un WebFetch directo
  a la URL exacta que vas a publicar. Si el fetch tiene éxito y el contenido
  coincide con lo que vas a describir (mismo programa, sigue activo), queda
  verificada.
- Si el entorno bloquea el fetch directo (`EGRESS_BLOCKED` u otro error de
  red — esto pasa seguido, ver notas de ejecuciones anteriores), NO caigas
  automáticamente a "confirmar por WebSearch y publicar igual". Una búsqueda
  solo confirma que la organización/programa existe en general; NO confirma
  que esa URL específica sigue viva hoy. Para publicar un link que no
  pudiste fetch en vivo, exige evidencia más fuerte:
  - Al menos una fuente de búsqueda **reciente** (idealmente del mismo año
    de la ejecución, o del ciclo/convocatoria vigente) que cite esa URL
    exacta como el link activo actual — no solo una mención histórica del
    programa.
  - Desconfía especialmente de URLs con rutas específicas de una cohorte,
    ciudad o año antiguo (ej. `/bog`, `/2022`, `/cohorte-3`) — estos
    patrones son los que más rápido quedan muertos cuando la organización
    lanza una nueva convocatoria con una página nueva. Prefiere siempre el
    link "canónico"/genérico más reciente de la organización (la página
    principal del programa) sobre un link de campaña vieja, aunque el link
    viejo haya aparecido en más resultados de búsqueda.
  - Si después de esto sigues sin poder confirmar con confianza razonable
    que el link específico sigue activo, **descarta la oportunidad** en vez
    de publicarla. Es preferible una categoría con menos tarjetas pero todas
    verificadas, que una lista más larga con riesgo de un link roto.
- Documenta en el comentario HTML de notas cuáles oportunidades se
  verificaron con fetch directo exitoso vs. cuáles se aceptaron solo con
  evidencia de búsqueda reciente (para que quede trazable qué tan sólida fue
  cada verificación).

Precedente: el 31 de agosto de 2026 se publicó un link de Laboratoria
(`postula.laboratoria.la/bog`) que resultó ser una página de postulación
descontinuada de una convocatoria de Bogotá de 2019-2022 (no el programa
vigente). Se había "verificado" solo por WebSearch tras un fetch bloqueado,
sin exigir evidencia de que esa URL puntual siguiera activa. La usuaria lo
detectó al hacer clic y reportó el error — ese tipo de falla es justo lo que
esta regla busca evitar.
