- La salida `Raster de pendiente` se puede usar luego como entrada de una herramienta de reclasificación.

---

### Salidas
Las **salidas** son los resultados finales del modelo que se generan al ejecutarlo.

- **Tipos de salidas:**
  - **Ráster:** mapas de elevación, pendientes, índices de vegetación.  
  - **Vectorial:** capas de puntos, líneas o polígonos resultantes de un análisis espacial.  
  - **Tabla:** resultados tabulados de estadísticas, conteos o resúmenes.

**Configuración de salidas:**

- Conecta la salida de la última herramienta a la sección de salidas del modelo.  
- Define **nombre** y **carpeta de guardado** para facilitar su localización.  
- Puedes usar una salida intermedia como entrada para otra herramienta dentro del mismo modelo.

**Ejemplo:**

Salida final: Mapa de pendiente reclasificada
Tipo: Ráster
Ruta de guardado: C:\Proyectos\Modelos\Pendientes.tif


---

### Conexión de elementos
- Cada elemento del modelo (entrada, herramienta o salida) se conecta mediante **flechas** que indican el flujo de datos.  
- Las salidas de una herramienta se pueden usar como entradas de otra, formando un **diagrama de flujo** claro y lógico.

**Consejo práctico:**
- Antes de agregar demasiadas herramientas, dibuja el flujo en papel o en un diagrama.  
- Mantén el canvas ordenado para que sea fácil entender el modelo a simple vista.

---

> **Tip:** Un buen modelo tiene entradas bien definidas, procesos intermedios claros y salidas descriptivas. Esto facilita su reutilización, mantenimiento y comprensión por otros usuarios.


