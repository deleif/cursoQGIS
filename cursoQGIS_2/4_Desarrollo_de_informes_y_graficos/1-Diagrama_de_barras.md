## 24.1.11.1. Diagrama de Barras

El algoritmo **Diagrama de Barras** crea un gráfico de barras a partir de una capa vectorial, utilizando una **categoría** y un **campo numérico**.  
Este tipo de gráfico resulta útil para representar comparaciones entre diferentes grupos o categorías dentro de un conjunto de datos espaciales.

---

### 🔧 Parámetros

| **Etiqueta** | **Nombre** | **Tipo** | **Descripción** |
|---------------|-------------|-----------|------------------|
| **Capa de entrada** | `INPUT` | [vector: geometría] | Capa vectorial de entrada. |
| **Nombre de campo de Categoría** | `NAME_FIELD` | [campo de tabla: cualquiera] | Campo categórico que se usará para agrupar las barras (eje **X**). |
| **Campo Valor** | `VALUE_FIELD` | [campo de tabla: cualquiera] | Valor numérico que se representará en el gráfico (eje **Y**). |
| **Diagrama de Barras** | `OUTPUT` | [html] | Archivo HTML donde se guardará el gráfico. Puede elegirse entre:<br> - **Guardar en archivo temporal**<br> - **Guardar en archivo…** |

---

### 📤 Salidas

| **Etiqueta** | **Nombre** | **Tipo** | **Descripción** |
|---------------|-------------|-----------|------------------|
| **Diagrama de Barras** | `OUTPUT` | [html] | Archivo HTML con el diagrama de barras. Se puede visualizar desde **Procesos → Visor de Resultados**. |

---


