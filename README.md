# Volcán Mombacho: timelapse satelital

Página web (`index.html`) con un control deslizante que recorre, en orden cronológico, las imágenes
históricas de **Esri World Imagery Wayback** del cráter, la cumbre y las antenas del volcán Mombacho
(Nicaragua). El periodo se elige en la página (por defecto, los últimos 7 años).

## Cómo abrirla
- Descarga `index.html` y ábrelo en Chrome, Edge o Firefox (necesita internet), o
- visita https://nsacasa.github.io/mombacho/ (una vez activado GitHub Pages).

Todo se calcula en el navegador al abrir la página, así que incluye automáticamente las imágenes nuevas que publique Esri.

## Qué hace
1. Descarga la lista de versiones de Wayback y, para cada una, consulta la **fecha real de captura** en el centro del encuadre.
2. Quita duplicados (muchas versiones repiten la misma imagen) y deja solo las capturas del periodo elegido
   (selector **Desde / Hasta** o atajos de 1, 3, 5, 7 o 10 años, o todo el archivo desde 2014).
3. Analiza los píxeles de la zona de análisis (rectángulo amarillo, de unos 2,6 km × 2,6 km) y clasifica cada píxel como vegetación,
   vegetación seca, suelo desnudo o derrumbe, nube o sombra.
4. **Descarta** las fechas en las que las nubes cubren más del umbral elegido (3 % por defecto).
5. Muestra la fecha sobre el mapa, la escala y la brújula, una gráfica de hectáreas afectadas y una tabla que se puede descargar en CSV.

## Parámetros por URL
`index.html?lat=11.8264&lon=-85.9681&km=2.6&from=2019-01-01&to=2026-11-11` (o `years=7` en lugar de `from`/`to`).
Al cambiar el periodo en la página, la dirección se actualiza: puedes compartir el enlace con ese periodo ya seleccionado.

## Limitaciones
- La clasificación usa solo color visible (RGB). Detecta pérdida de vegetación, que es un indicador indirecto, pero **no mide temperatura**.
  Para confirmar calentamiento hace falta imagen térmica (Landsat 8/9, banda 10).
- Cada versión viene de un satélite distinto, con colores distintos. Ajusta los umbrales con “Mostrar clasificación”.
- La fecha corresponde a la imagen en el centro del encuadre. Algunas versiones son mosaicos de varias fechas.

Imágenes: Esri, Maxar, Earthstar Geographics y la comunidad de usuarios de SIG.
