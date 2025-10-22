# 24.1.11.3. Diagrama de media y desviación estándar

Crea un diagrama de caja con valores media y desviación estándar.

## Parámetros

| Etiqueta | Nombre | Tipo | Descripción |
|----------|--------|------|-------------|
| Tabla de entrada | INPUT | [vector: geometría] | Capa de vector de entrada |
| Nombre de campo de Categorías | NAME_FIELD | [campo de tabla: cualquiera] | Campo de categorías a usar para agrupar las cajas (eje X) |
| Campo Valor | VALUE_FIELD | [campo de tabla: numérico] | Valor a usar para el diagrama (Eje Y). |
| Diagrama | OUTPUT | [html] | Predeterminado: [Save to temporary file]. Especifique el archivo HTML para el gráfico. Uno de: Guardar en Archivo Temporal, Guardar en archivo… |

## Salidas

| Etiqueta | Nombre | Tipo | Descripción |
|----------|--------|------|-------------|
| Diagrama | OUTPUT | [html] | Archivo HTML con el diagrama. Disponible en Procesos -> Visor de Resultados. |


