# Ejercicio

La Diputación Provincial de Zaragoza tiene que invertir un presupuesto extraordinario en asfaltar
un tramo de carretera localizado la provincia de Zaragoza, concretamente en la comarca de Tarazona y el Moncayo.

El equipo responsable del proyecto debe seleccionar un tramo para la actuación, que deberá cumplr los siguientes requisitos:

## Selección de la zona de actuación:

- Debe pertenecer a una carretera de cuya titularidad corresponda a la DPZ.
- No debe afectar a ninguna de las siguientes Figuras de Protección de la Naturaleza, incluyendo su Área de Influencia Socioeconómica:
  - Espacios Naturales Protegidos.
  - Red Natura 2000: Zonas de Especial Conservación (ZEC) y Zonas de ESpecial Protección para las Aves (ZEPA).
  - Áreas de Influencia Socioeconónica de los ENPs.
- Debe estar a más de 500 metros de la red fluvial cuyo orden en la clasificación Strahler sea superior a 1.
- El tramo debe medir más de 1000 metros de longitud.

Si existieran varios tramos que cumpliesen los criterios, se seleccionará el que esté más próximo a un punto de control.

La actuación tendrá en cuenta una ocupación temporal de 20 metros a cada lado de la carretera.

Se deberá elaborar una ficha para cada una de las parcelas catastrales afectadas por la actuación, que incorporará un mapa
con la parcela afectada por la actuación, la superficie de ocupación temporal e información adicional de interés.
Las capas resultantes deberán ser empaquetas en un archivo Geopackage.

Adicionalmente se debe responder a las siguientes cuestiones:

- Superficie de ocupación temporal y definitiva de cada parcela.
- Municipio en el que se localiza la actuación y su población.

Para ello, se dispone de la siguiente información:

## Listado de coordenadas de puntos de control:

| ID  | Nombre       | X      | Y       |
| --- | ------------ | ------ | ------- |
| 1   | El Bustiño   | 612973 | 4641057 |
| 2   | Morón        | 604363 | 4622403 |
| 3   | Cañada Pozón | 104096 | 4656311 |

## Fuentes de datos geográficos:

- Servicio WFS del Gobierno de Aragón: https://idearagon.aragon.es/Visor2D
- Servicio WMS de Catastro: https://ovc.catastro.meh.es/Cartografia/WMS/ServidorWMS.aspx

Instituto Geográfico Nacional:
- Ortofoto PNOA : http://www.ign.es/wms-inspire/pnoa-ma
- Mapa Topográfico Nacional: http://www.ign.es/wms-inspire/mapa-raster
- Nombres Geográficos: https://www.ign.es/wms-inspire/ngbe
  
## Fuente de datos demográficos:

- Instituto Naciona de Estadística: https://www.ine.es/jaxiT3/Tabla.htm?t=2907&L=0
