## 4. Variables en el Model Builder

Las **variables** permiten almacenar temporalmente valores dentro del modelo para ser reutilizados en distintas herramientas o cálculos. Son especialmente útiles cuando necesitamos usar **valores intermedios** como entrada en otra herramienta.

### Tipos de variables

1. **Variables de entrada:**  
   - Se definen al crear las entradas del modelo.  
   - Pueden ser ráster, vector, número, texto o booleano.

2. **Variables intermedias:**  
   - Resultados generados por herramientas dentro del modelo.  
   - Se usan como entrada para otros procesos sin necesidad de generar un archivo físico.

3. **Variables de salida:**  
   - Resultados finales que se guardan y se pueden usar fuera del modelo.

### Ejemplo práctico
Supongamos que tenemos un raster de pendiente y queremos normalizar sus valores:

[MDE] --> [Calcular pendiente] --> [Variable intermedia: Pendiente_max] --> [Calculadora raster] --> [Salida: Pendiente normalizada]


- `Pendiente_max` almacena el valor máximo de pendiente calculado y se pasa a la **calculadora raster** como parámetro para normalizar todos los valores de pendiente.

> Tip: Mantén nombres claros para las variables, así sabes qué representa cada una durante la ejecución del modelo.
