# Deformación superficial asociada a movimientos en masa en la cuenca media y baja del río Suárez (InSAR y GNSS)

## Cuadernos

Se corren en este orden, porque cada uno usa las salidas del anterior:

| Cuaderno | Qué hace |
|---|---|
| `notebooks/01_procesamiento_insar.ipynb` | Descarga los interferogramas de Sentinel-1 procesados en HyP3, los recorta, arma las series temporales con MintPy (corrección troposférica con ERA5, rampas, error de DEM y sesgo de cierre) y calcula la velocidad en la línea de vista, la componente regional y la velocidad local. |
| `notebooks/02_procesamiento_gnss.ipynb` | Descarga las series diarias del Nevada Geodetic Laboratory, ajusta el modelo de trayectoria con saltos, sismos y señal estacional, estima el ruido y calcula las velocidades, también con MIDAS. |
| `notebooks/03_integracion_gnss_insar.ipynb` | Recalcula la velocidad GNSS en el periodo de las imágenes, la proyecta a la línea de vista y la compara con el InSAR. |
| `notebooks/04_figuras_y_capas_sig.ipynb` | Delimita y clasifica las zonas de deformación activa, las cruza con el SIMMA, la amenaza, la geología, las fallas y la cobertura, y genera las figuras del documento, las fichas de los Apéndices A y C y las capas para SIG y Google Earth. |

## Carpetas

- `01_datos`: insumos descargados (área de estudio, pares de HyP3, GNSS, cobertura, amenaza).
- `02_mintpy`: carpetas de trabajo de MintPy por stack.
- `03_resultados`: GeoTIFF, tablas, figuras, zonas de deformación activa, capas para SIG y fichas.

Los interferogramas de HyP3 y las carpetas de MintPy pesan cerca de 390 GB y no se suben al repositorio (ver `.gitignore`); los cuadernos los vuelven a descargar o calcular.

## Datos de entrada

Sentinel-1 procesado en HyP3 (Alaska Satellite Facility), modelo Copernicus GLO-30, reanálisis ERA5 (Copernicus Climate Data Store, requiere el archivo `~/.cdsapirc`), series GNSS del Nevada Geodetic Laboratory, Mapa Geológico de Colombia 2023, inventario SIMMA y mapas de amenaza por movimientos en masa 1:100 000 del Servicio Geológico Colombiano, ESA WorldCover 2021, lluvia CHIRPS, catálogo sísmico del USGS e imágenes Esri World Imagery para las fichas. Las fuentes completas están en la lista de referencias del documento.

## Entorno

Los cuadernos se corrieron en OpenSARLab (Alaska Satellite Facility) con Python 3. Los paquetes del núcleo están en `requirements.txt`; MintPy, PyAPS y PySolid se instalan en un entorno conda aparte desde el cuaderno 1.

## Cómo citar

Paredes Galindo, M. y Granada Garzón, S. (2026). *Evaluación de la deformación superficial asociada a movimientos en masa mediante análisis InSAR y datos GNSS en la cuenca media y baja del río Suárez, Colombia* [Trabajo de grado, Universidad Industrial de Santander].
