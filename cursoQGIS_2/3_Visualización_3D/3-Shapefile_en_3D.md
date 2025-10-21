# Shapefile en 3D con QGIS2threejs

A continuación se explica cómo representar un *shapefile* (por ejemplo, polígonos o edificios) en 3D mediante **extrusión**.

---

## Pasos para visualizar un shapefile en 3D

1. **Abrir la vista 3D**
   - Menú: `Web → QGIS2threejs → Export to Web`
   - Se abrirá la ventana del complemento con varias pestañas (Scene, DEM, Vector, etc.).

2. **Activar la capa en la vista 3D**
   - En la pestaña **Vector**, marca la casilla de la capa que deseas mostrar.
   - Solo las capas activadas aquí se visualizarán en el modelo 3D.

3. **Configurar las propiedades del objeto**
   - Selecciona la capa y pulsa el botón **Properties** (o haz clic derecho → *Properties*).
   - En el apartado **Object type**, elige:
     ```
     Extruded
     ```
     Esto permitirá dar volumen a los polígonos (por ejemplo, edificios o parcelas).

4. **Definir la altura (extrusión)**
   - En el campo **Height**, puedes:
     - Introducir un valor fijo (por ejemplo, `20` metros), o
     - Usar un campo de atributo de la capa .

5. **Ajustar la elevación sobre el terreno**
   - En el apartado **Z coordinate**, selecciona:
     ```
     Relative to DEM
     ```
     De esta forma, el shapefile se apoyará sobre el modelo digital del terreno (MDE) y se ajustará a su relieve.


---



