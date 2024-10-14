
# Módulo: Channel Network and Drainage Basins

https://saga-gis.sourceforge.io/saga_tool_doc/2.2.4/ta_channels_5.html


## Parámetros

| Nombre                     | Tipo                  | Identificador | Descripción                               | Restricciones         |
|----------------------------|-----------------------|---------------|-------------------------------------------|-----------------------|
| Input Elevation        | Grid (entrada)  | `DEM`         |                                           | -                     |
| Flow Direction          | Grid (salida opcional) | `DIRECTION`   |                                           | -                     |
| Flow Connectivity       | Grid (salida opcional) | `CONNECTION`  |                                           | -                     |
| Strahler Order           | Grid (salida opcional) | `ORDER`       |                                           | -                     |
| Drainage Basins         | Grid (salida opcional) | `BASIN`       |                                           | -                     |
| Channel Segments          | shp (salida)       | `SEGMENTS`    |                                           | -                     |
|  Basin Shapes          | shp (salida)       | `BASINS`      |                                           | -                     |
| Junctions                    | shp (salida opcional) | `NODES`       |                                           | -                     |
| Options                   |                       |               |                                           |                       |
| Umbral                     | Entero                | `THRESHOLD`   | Orden de Strahler para iniciar un canal. Mínimo: 1, Threshold: 5 |



Stahler Order jerarquiza los cursos de agua, clasificándolos en función de su posición dentro de la red de drenaje. Este método clasifica los tramos de ríos de la siguiente manera:

    - Los arroyos más pequeños sin tributarios son asignados como de orden 1.
    - Cuando dos arroyos de orden 1 se unen, el nuevo tramo resultante es de orden 2.
    - Dos tramos de orden 2 se combinan para formar uno de orden 3, y así sucesivamente.

* Comparar resultado final con r.watershed.

