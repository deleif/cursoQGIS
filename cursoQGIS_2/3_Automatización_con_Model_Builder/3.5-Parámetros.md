## 5. Parámetros de modelo

Los **parámetros** son valores que el usuario debe proporcionar al ejecutar el modelo. Son similares a las entradas, pero se enfocan en **controlar cómo se ejecutan las herramientas**.

### Tipos de parámetros

- **Ráster/vector de entrada:** capas que se usarán en los procesos.  
- **Valores numéricos:** umbrales, porcentajes, distancias, pendientes máximas.  
- **Opciones booleanas:** activar o desactivar funcionalidades dentro del modelo.  
- **Texto:** nombres de archivos, etiquetas o comentarios.

### Uso de parámetros para cálculos
En un modelo que normaliza pendientes:

1. Entrada: `Raster de pendiente`  
2. Parámetro: `Pendiente máxima` (valor que se puede calcular previamente o introducir manualmente)  
3. Calculadora raster: `(Pendiente_actual / Pendiente_maxima) * 100`

> Esto permite que los valores del raster se normalicen automáticamente de 0 a 100%.

**Consejo práctico:**
- Cuando un valor depende de otro cálculo dentro del modelo, usa **variables intermedias** y pásalas como parámetro.  
- Evita valores fijos cuando sea posible; así el modelo será más flexible y reutilizable.
