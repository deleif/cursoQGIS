# 24.1.11.4. Diagrama polar

Genera un diagrama polar basado en el valor de una capa de vector de entrada.

Se deben ingresar dos campos como parámetros: uno que define la categoría de cada objeto (para agrupar objetos) y otro con la variable a graficar (esta debe ser numérica).

## Parámetros

| Etiqueta | Nombre | Tipo | Descripción |
|----------|--------|------|-------------|
| Capa de entrada | INPUT | [vector: geometría] | Capa de vector de entrada |
| Nombre de campo de Categorías | NAME_FIELD | [campo de tabla: cualquiera] | Campo de categorías a usar para agrupar las entidades (eje X) |
| Campo Valor | VALUE_FIELD | [campo de tabla: numérico] | Valor a usar para el diagrama (Eje Y). |
| Diagrama polar | OUTPUT | [html] | Predeterminado: [Save to temporary file]. Especifique el archivo HTML para el gráfico. Uno de: Guardar en Archivo Temporal, Guardar en archivo… |

## Salidas

| Etiqueta | Nombre | Tipo | Descripción |
|----------|--------|------|-------------|
| Diagrama polar | OUTPUT | [html] | Archivo HTML con el diagrama. Disponible en Procesos -> Visor de Resultados. |


