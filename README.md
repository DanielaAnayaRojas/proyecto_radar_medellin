# Radar Medellín

Reporte diario automatizado de oportunidades activas (becas, cursos, convocatorias y eventos) para Colombia y Latinoamérica, o de modalidad 100% virtual sin restricción de país.

Cada mañana a las 8:00 a.m. (hora Colombia) se genera un reporte en HTML con las oportunidades vigentes en tres categorías:

- 🌿 Botánica floral y conservación
- 🌍 Cambio climático y mitigación
- 🎓 Becas y cursos de IA / educación

## Ver el reporte de hoy

👉 **https://danielaanayarojas.github.io/proyecto_radar_medellin/**

## Cómo funciona

Una rutina programada investiga oportunidades activas en fuentes oficiales (universidades, jardines botánicos, ONG como UICN/WWF/BGCI, portales de becas como Colfuturo, ICETEX, DAAD, Chevening, Fulbright y Erasmus+, entre otras), descarta cualquier link que no pueda verificar y genera un reporte con:

- Solo oportunidades con inscripción abierta y no vencidas.
- Primero las gratuitas, luego las de pago; dentro de cada grupo, ordenadas por fecha de cierre más próxima.
- Un resumen de una frase por oportunidad, redactado por el modelo (nunca copiado literal de la fuente).
- Diseño Material Design 3 (tipografía Roboto, colores vivos, tarjetas redondeadas).

## Estructura del repositorio

```
├── index.html              # Reporte del día actual (lo que muestra GitHub Pages)
└── reportes/
    └── YYYY-MM-DD.html      # Histórico: un archivo por cada día que corrió la rutina
```

`index.html` en la raíz se sobrescribe cada día con el contenido más reciente; los archivos dentro de `reportes/` se conservan como archivo histórico.

## Publicación

El sitio se sirve con **GitHub Pages** desde la rama `main`, carpeta raíz (`/`).

## Limitaciones conocidas

Algunas ejecuciones corren en un entorno sin salida a internet para verificación en vivo de enlaces (WebFetch bloqueado por política de red). En esos casos, las URLs provienen de resultados de búsqueda reales (nunca inventadas), pero no se abrieron en vivo para confirmar que siguen activas. Cuando esto ocurre, queda documentado en un comentario HTML al final del reporte del día correspondiente.
