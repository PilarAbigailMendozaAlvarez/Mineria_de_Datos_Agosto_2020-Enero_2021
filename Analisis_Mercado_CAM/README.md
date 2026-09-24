# Estudio de mercado CAM – San Lucas y San José

Evalúa el potencial de mercado para instalar un **CAM (Centro de Atención Médica)** tomando como zona de influencia
los establecimientos a **≤ 30 minutos de traslado** (se mide en tiempo, no en km).

| Notebook | Establecimientos | Tiempo de traslado | Mapa | Costo |
|---|---|---|---|---|
| `CAM_Mercado_GoogleMaps.ipynb` | Google Places API (New) | Google Routes API (con tráfico) | Google Maps JavaScript API | Clave de Google Cloud (crédito mensual gratuito) |
| `CAM_Mercado_Gratuito.ipynb` | DENUE (INEGI) + OpenStreetMap | OSRM (sin tráfico, factor ajustable) + zona isócrona | Folium / OpenStreetMap | Gratis (token DENUE gratuito) |

## Qué genera cada notebook
- **5 mapas por ubicación**: uno general y uno por categoría (CAM de consulta externa, clínicas de especialidad,
  laboratorios y gabinetes de imagen). El icono indica la categoría y el color el subtema (por ejemplo, laboratorio
  de **cadena** – Chopo, Salud Digna u otra nacional – frente a laboratorio **local**). Cada subtema se puede ocultar o mostrar.
- **Excel por ubicación**: metodología, resumen por subtema y banda de tiempo (0-10, 10-20 y 20-30 min), y una hoja por categoría con
  los campos del estudio (nombre, dirección, horarios, especialidades, laboratorio o imagen en el sitio, cadena y sucursales,
  tipos de estudio, etc.).
- **Excel comparativo** San Lucas vs San José.

## Uso
1. Define `GOOGLE_MAPS_API_KEY` (versión Google) o `DENUE_TOKEN` (versión gratuita) como variable de entorno,
   o pégalos en la celda de configuración.
2. Ejecuta todas las celdas. Los enlaces `maps.app.goo.gl` se convierten solos a coordenadas; si tu red no lo
   permite, escribe `lat`/`lng` en `UBICACIONES`.
3. Los resultados quedan en `salidas_google/` o en `salidas_gratuito/`.

Ninguna fuente publica de forma sistemática el número de consultorios ni el de médicos: esas columnas quedan marcadas
como *"validar en campo"* (en la versión gratuita se incluye el estrato de personal ocupado que reporta el DENUE como referencia).
