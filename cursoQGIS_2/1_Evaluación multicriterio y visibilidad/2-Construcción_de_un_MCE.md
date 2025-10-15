# 2. Construcción de un MCE completo – 1h

## 2.1 Integración de factores y restricciones

### Concepto

Una vez normalizados los factores y definidas las restricciones, el siguiente paso es combinarlos para generar un **mapa de idoneidad o aptitud**:

- **Combinar capas normalizadas**:  
  - Se utilizan operaciones algebraicas (suma ponderada) en **Raster Calculator**.  
  - Ejemplo:  
    ```
    ("pendiente_norm" * 0.5) + ("distancia_norm" * 0.3) + ("vegetacion_norm" * 0.2)
    ```
  - Resultado: raster donde valores más altos indican mayor idoneidad.  

- **Aplicar restricciones**:  
  - Generar máscaras para excluir áreas inviables (valor=0).  
  - Se puede hacer multiplicando el raster de idoneidad por el raster de restricción (0=prohibido, 1=permitido).  
  - Ejemplo:  
    ```
    "idoneidad_preliminar" * "mascara_restricciones"
    ```

### Ejercicio práctico

**Objetivo:** crear un mapa de idoneidad para construcción.  
**Datos:** raster de pendiente, distancia a carreteras, cobertura vegetal y vector de zonas protegidas.  

Pasos:  
1. Normalizar cada raster de factor (0–1).  
2. Crear máscara de restricciones: raster binario (1 = área permitida, 0 = zona protegida).  
3. Combinar factores normalizados mediante Raster Calculator usando ponderaciones iniciales (ej. 0.5, 0.3, 0.2).  
4. Multiplicar resultado por la máscara de restricciones.  
5. Visualizar el mapa final de idoneidad en QGIS con rampa de colores.  

---

## 2.2 Aplicación de ponderaciones

### Concepto

En un análisis multicriterio, no todos los factores tienen la misma relevancia para la decisión final.

Por ejemplo, en la elección de zonas aptas para la reforestación, la pendiente puede ser más determinante que la orientación, o la proximidad a ríos más importante que la altitud.

- Cada factor puede tener diferente importancia relativa en la decisión.  
- Los pesos reflejan esta importancia y modifican el resultado final del mapa de aptitud. Así, cada mapa normalizado aporta al resultado final en función de su peso. 

### Métodos

#### Escalas lineales o porcentuales
- Método sencillo y directo.  
- Se asignan valores de peso entre **0 y 1**, o porcentajes que suman **1 o 100**.

Ejemplo:

| Factor             | Peso (%) | Peso (0–1) |
|--------------------|-----------|------------|
| Pendiente          | 40        | 0.40       |
| Suelo              | 30        | 0.30       |
| Orientación        | 20        | 0.20       |
| Proximidad a agua  | 10        | 0.10       |
| **Total**          | **100**   | **1.00**   |

Cuanto mayor el peso, mayor la influencia del factor en el mapa final.


#### Método AHP (Analytic Hierarchy Process)
- Se basa en **comparaciones pareadas** entre factores: cada par de criterios se evalúa según su importancia relativa (de 1 a 9).  
- Permite obtener los pesos de forma **justificada y coherente**, en lugar de asignarlos de manera arbitraria.

**Pasos básicos del AHP:**

1. **Definir los factores** del análisis (por ejemplo: pendiente, suelo, orientación, distancia a ríos).  
2. **Construir la matriz de comparaciones pareadas**, evaluando la importancia relativa de cada par de factores.  
   - Se usan valores de 1 a 9 según la escala de Saaty:  
     - 1 → igual importancia  
     - 3 → importancia moderada  
     - 5 → importancia fuerte  
     - 7 → importancia muy fuerte  
     - 9 → importancia extrema  
     - (y sus recíprocos 1/3, 1/5, etc.)  
3. **Completar toda la matriz**, de forma que cada celda (i, j) refleje la comparación entre los factores *i* y *j*.  
4. **Calcular el vector de pesos** (autovector principal normalizado).  
5. **Comprobar la consistencia** de las comparaciones mediante el **Índice de Consistencia (CI)**:  
   - CI = (λ_max – n) / (n – 1)  
   - Donde **λ_max** es el autovalor máximo y **n** el número de factores.  
   - Si **CI / RI < 0.1**, la matriz se considera **consistente** (RI = índice aleatorio de Saaty).  
6. **Aplicar los pesos resultantes** en la combinación ponderada de los factores normalizados.

**Ejemplo** 

Supongamos tres factores: **pendiente (P)**, **suelo (S)** y **distancia a ríos (R)**.  

| Comparación | Valor asignado | Interpretación |
|--------------|----------------|----------------|
| P vs S | 3 | Pendiente es moderadamente más importante que suelo |
| P vs R | 5 | Pendiente es fuertemente más importante que distancia a ríos |
| S vs R | 2 | Suelo es ligeramente más importante que distancia a ríos |

Matriz de comparación:

| Factor | Pendiente | Suelo | Distancia a ríos |
|:-------|:-----------|:------|:-----------------|
| **Pendiente** | 1 | 3 | 5 |
| **Suelo** | 1/3 | 1 | 2 |
| **Distancia a ríos** | 1/5 | 1/2 | 1 |

Después del cálculo (normalización y autovector):

| Factor | Peso (0–1) | Peso (%) |
|---------|-------------|-----------|
| Pendiente | 0.63 | 63% |
| Suelo | 0.26 | 26% |
| Distancia a ríos | 0.11 | 11% |
| **Total** | **1.00** | **100%** |


### Herramientas en QGIS

- **Raster Calculator**: multiplicar cada factor normalizado por su peso y sumar.  
