# 24.1.11.6. Histograma de capa vectorial

Genera un histograma con los valores del atributo de una capa vectorial.

El atributo a usar para el cómputo del histograma debe ser genérico.

## Parámetros

| Etiqueta | Nombre | Tipo | Descripción |
|-----------|---------|------|-------------|
| Capa de entrada | INPUT | [vectorial: cualquiera] | Capa de vector de entrada |
| Atributo | FIELD | [campo de tabla: numérico] | Valor a usar para el diagrama (Eje Y). |
| número de cajas | BINS | [numérico: entero] | Predeterminado: 10<br>El número de cajas a usar en el histograma (eje X). Mínimo 2. |
| Histograma | OUTPUT | [html] | Predeterminado: [Save to temporary file]<br>Especifique el archivo HTML para el gráfico. Uno de:<br><br>Guardar en Archivo Temporal<br>Guardar en archivo… |

## Salidas

| Etiqueta | Nombre | Tipo | Descripción |
|-----------|---------|------|-------------|
| Histograma | OUTPUT | [html] | Archivo HTML con el diagrama. Disponible en Procesos -> Visor de Resultados. |

