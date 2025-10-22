# 24.1.11.5. Histograma capa Ráster

Genera un histograma con los valores de una capa ráster.

## Parámetros

| Etiqueta | Nombre | Tipo | Descripción |
|-----------|---------|------|-------------|
| Capa de entrada | INPUT | [raster] | Capa ráster de entrada |
| Número de banda | BAND | [banda ráster] | Banda ráster a usar para el histograma |
| número de cajas | BINS | [numérico: entero] | Predeterminado: 10<br>El número de cajas a usar en el histograma (eje X). Mínimo 2. |
| Histograma | OUTPUT | [html] | Predeterminado: [Save to temporary file]<br>Especifique el archivo HTML para el gráfico. Uno de:<br><br>Guardar en Archivo Temporal<br>Guardar en archivo… |

## Salidas

| Etiqueta | Nombre | Tipo | Descripción |
|-----------|---------|------|-------------|
| Histograma | OUTPUT | [html] | Archivo HTML con el diagrama. Disponible en Procesos -> Visor de Resultados. |

## Código Python

Algoritmo ID: `qgis:rasterlayerhistogram`


