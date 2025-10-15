## 6. Ejecutar, depurar y compartir

Una vez creado un modelo, es fundamental saber **cómo ejecutarlo**, **detectar errores** y **compartirlo** con otros usuarios o proyectos.

---

### Ejecutar modelos
1. Guarda el modelo antes de ejecutarlo.  
2. Desde la **Caja de herramientas**, busca el modelo por su nombre o grupo.  
3. Haz doble clic sobre el modelo para abrir la ventana de ejecución.  
4. Introduce los **valores de entrada y parámetros** solicitados:  
   - Capas raster/vectoriales.  
   - Valores numéricos o booleanos según lo definido en el modelo.  
5. Haz clic en **Ejecutar** y espera a que el proceso termine.

> Tip: Si el modelo genera varios resultados intermedios, puedes optar por **guardar solo la salida final** para ahorrar espacio.

---

### Depuración de errores
Al ejecutar un modelo pueden aparecer errores o resultados inesperados. Algunas estrategias para depurar:

- **Revisar variables intermedias:**  
  Asegúrate de que cada variable contiene los datos correctos antes de pasar al siguiente paso.
  
- **Verificar parámetros de entrada:**  
  Comprueba que los datos suministrados cumplen los tipos y formatos esperados (raster, vector, número, texto).

- **Leer mensajes de error:**  
  QGIS proporciona mensajes de error que indican qué herramienta falló y por qué.  
  Ejemplos comunes:
  - Entrada no encontrada.  
  - Valores fuera de rango.  
  - Formato de archivo no compatible.

- **Probar con subconjuntos de datos:**  
  Ejecuta el modelo con un pequeño conjunto de datos antes de aplicarlo a todo el proyecto.

---

### Compartir modelos
Los modelos pueden ser compartidos y reutilizados en otros proyectos:

1. **Exportar modelo:**  
   - Selecciona el modelo en el Diseñador y usa la opción **Exportar**.  
   - Se guarda como archivo `.model3` que puede importarse en otro QGIS.

2. **Importar modelo:**  
   - Desde otro proyecto, abre el Diseñador de modelos y usa **Importar** para cargar el archivo `.model3`.

3. **Uso en otros proyectos o por otros usuarios:**  
   - Asegúrate de que los usuarios tengan acceso a las mismas herramientas y formatos de datos.  
   - Añade una **descripción clara** y documentación de parámetros y salidas para facilitar su reutilización.

---

### Consejos prácticos
- Mantén los modelos bien organizados por **grupos y nombres claros**.  
- Documenta **cada entrada, variable y salida**.  
- Haz copias de seguridad de modelos complejos antes de modificarlos.  
- Aprovecha la depuración para aprender a **optimizar y simplificar** los flujos de trabajo.

---

> **Tip final:** Un modelo no solo automatiza procesos, sino que también sirve como **documentación visual de tus análisis espaciales**, facilitando la comprensión, la reproducibilidad y el intercambio con otros usuarios.
