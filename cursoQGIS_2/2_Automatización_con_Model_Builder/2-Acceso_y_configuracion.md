## 2. Acceso y configuración

### Acceso al Diseñador de modelos
Para abrir el Diseñador de modelos en QGIS:

1. En la barra de menú, seleccionar:  

Procesos > Modelador de procesos
2. Se abrirá la ventana del **Model Builder**, lista para crear y configurar modelos.

---

### Interfaz del Modelador de procesos
El Diseñador de modelos tiene varios elementos principales:

#### 1. Panel de herramientas
- Muestra la **lista de procesos disponibles** en QGIS, tanto nativos como de terceros (por ejemplo, GDAL, GRASS, SAGA).  
- Permite **arrastrar y soltar** herramientas dentro del canvas para agregarlas al modelo.

#### 2. Canvas (lienzo)
- Área central donde se **conectan las entradas, herramientas y salidas**.  
- Se visualiza el flujo de trabajo como un **diagrama de bloques**, mostrando cómo los datos se transforman paso a paso.

#### 3. Panel de entradas y salidas
- Aquí se definen los **parámetros de entrada** del modelo y las **salidas finales**.  
- Permite configurar:
- Nombre y tipo de entrada (Raster, Vector, Número, Texto, Booleano).  
- Salida generada por cada herramienta dentro del modelo.

---

### Configurar un modelo
Al crear un modelo, es importante definir sus propiedades generales:

1. **Nombre del modelo**  
- Debe ser claro y descriptivo, por ejemplo:  
  ```
  Modelo de análisis de pendientes
  ```

2. **Grupo**  
- Categoría donde se almacenará el modelo en la **Caja de herramientas**.  
- Permite organizar múltiples modelos por temática.

3. **Descripción**  
- Breve explicación de la finalidad del modelo y los datos que requiere.  
- Útil para otros usuarios o para ti mismo cuando reutilices el modelo.

4. **Carpeta de guardado**  
- Directorio donde se almacenará el archivo del modelo (`.model3` o similar).  
- Recomendada una ubicación dentro de tu proyecto para facilitar la reutilización y el intercambio.

---

### Consejos prácticos de configuración
- Siempre asigna **nombres descriptivos** a entradas y salidas; evita abreviaturas ambiguas.  
- Añade **descripciones** en cada parámetro para recordar su función y tipo de datos esperado.  
- Organiza los modelos en **grupos lógicos** para encontrarlos fácilmente en la caja de herramientas.  
- Guarda frecuentemente el modelo mientras lo desarrollas para evitar pérdida de información.

---

> **Tip:** Antes de agregar múltiples herramientas, prueba crear un modelo **muy sencillo** (por ejemplo: cargar un raster y generar su pendiente) para familiarizarte con la interfaz y el flujo de conexión de elementos.
