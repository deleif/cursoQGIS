
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


# 🧩 Parámetros de entrada

## 🗺️ **Elevation**
- **Descripción:** DEM de entrada.  
  Normalmente se selecciona el **“Filled DEM”** obtenido del algoritmo *Fill Sinks (Wang & Liu)*.  
  Debe ser un modelo **sin depresiones**, para garantizar que los flujos sean continuos.

---

## 🔢 **Threshold**
Uno de los parámetros más importantes.  
Define el **número mínimo de celdas acumuladas** necesarias para considerar que el flujo forma un canal.

### 💬 En otras palabras:
- Cuanto **menor** el valor → más canales se generan (red más densa).  
- Cuanto **mayor** el valor → menos canales (solo los principales).

### 💡 Ejemplos:
- `Threshold = 5` → incluso pequeñas acumulaciones generan canales.  
- `Threshold = 100` → solo las zonas con acumulación significativa se convierten en ríos.

### 📏 Depende del tamaño de píxel del DEM:
| Resolución DEM | Umbral recomendado |
|-----------------|--------------------|
| 1 m             | 500–2000           |
| 25 m            | 5–50               |

---

## 🟦 **Subbasins**
Si se activa esta opción, además de las cuencas principales, el algoritmo **delimita subcuencas** para cada confluencia o canal importante.  
Esto **divide las grandes cuencas en unidades más pequeñas** y manejables.

---

## 💧 **Flow Direction**
Ráster que indica la **dirección del flujo** en cada celda.  
Usualmente se codifica con valores **1–8**, según el esquema **D8**.  
Sirve para calcular **acumulaciones** y definir el **sentido de los canales**.

---

## 🔗 **Flow Connectivity**
Ráster que muestra la **conectividad del flujo**, es decir, si una celda pertenece a una ruta de drenaje continua o aislada.  
Útil para **detectar áreas donde el flujo se interrumpe o desconecta**.

---

## 🔢 **Strahler Order**
Ráster que asigna a cada canal un **orden jerárquico** según el método de **Strahler**:

- Canales sin afluentes → **orden 1**  
- Unión de dos canales de orden 1 → **orden 2**  
- Unión de dos canales de orden 2 → **orden 3**, y así sucesivamente  

👉 Permite **identificar los ríos principales y secundarios**.

---

## 🟫 **Drainage Basins**
Ráster que muestra las **cuencas de drenaje** delimitadas automáticamente.  
Cada cuenca se **etiqueta con un número entero distinto**.  
Representa el **área que vierte hacia un canal o punto de salida**.

---

## 🩵 **Channels**
Capa **ráster o vectorial** que representa la **red de canales (ríos)** detectados según el *threshold*.  
Cada celda con flujo superior al umbral se marca como canal.  

👉 Es la salida más visual: **los ríos generados automáticamente a partir del relieve.**

---

## ⚫ **Junctions**
Capa **ráster o vectorial** (según la versión) que marca los **puntos de confluencia entre canales**.  
Cada *junction* es un **nodo donde se unen dos o más flujos**.  
Útil para crear una **red de drenaje topológicamente conectada**.

---

# En resumen

| 🏷️ **Campo**          | 💡 **Qué es**                                      | 📦 **Qué produce**                |
|------------------------|---------------------------------------------------|----------------------------------|
| **Elevation**          | DEM sin depresiones                              | Base del análisis                |
| **Threshold**          | Mínimo de acumulación para formar canal          | Controla densidad de red         |
| **Subbasins**          | Activa la generación de subcuencas               | Más detalle                      |
| **Flow Direction**     | Dirección del flujo (D8)                         | Ráster auxiliar                  |
| **Flow Connectivity**  | Continuidad del flujo                            | Ráster auxiliar                  |
| **Strahler Order**     | Orden jerárquico de canales                      | Ráster                           |
| **Drainage Basins**    | Cuencas de drenaje (áreas)                       | Ráster                           |
| **Channels**           | Red de canales                                   | Ráster principal                 |
| **Junctions**          | Puntos donde confluyen canales                   | Ráster / puntos                  |
