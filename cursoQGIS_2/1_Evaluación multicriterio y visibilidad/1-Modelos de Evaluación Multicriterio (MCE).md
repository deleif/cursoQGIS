# 1. Modelos de Evaluación Multicriterio (MCE) – 1h

## Objetivos específicos

- Comprender la diferencia entre **factores** y **restricciones** en análisis espacial.  
- Conocer y aplicar los principales métodos de **normalización** de capas raster.
- Comprender la importancia de la **ponderación** y cómo aplicarla en QGIS para generar mapas de aptitud.  
- Analizar cómo la elección de métodos de normalización y ponderación afecta los resultados finales.  

---

## 1.1 Factores y restricciones

### Concepto y distinción

- **Factores**: representan **criterios de decisión** que influyen en el resultado de manera positiva o negativa.  
  - Características:
    - Son cuantitativos o cualitativos convertibles a escala numérica.  
    - Se transforman a **escala 1–100**.  
  - Ejemplos:  
    - Pendiente del terreno (menos pendiente → más apto).  
    - Distancia a carreteras (más cercano → más apto).  
    - Tipo de suelo (ciertos tipos son más favorables).  

- **Restricciones**: representan **áreas donde la decisión es inviable**.  
  - Características:
    - Se aplican como máscara: valores dentro de la restricción reciben **0**.  
  - Ejemplos:  
    - Zonas protegidas.  
    - Áreas inundables.  
    - Suelos contaminados.  

**Ejemplo práctico conceptual:**  
Ubicación de un polígono industrial:  
- Factores: pendiente <15%, distancia a carreteras <500 m, suelo estable.  
- Restricciones: parques naturales, ríos, áreas residenciales.  

---

## 1.2 Normalización de valores

### 1.2.1 Por qué es necesaria la normalización

- Factores tienen unidades distintas (metros, %, índices).  
- Si se combinan sin transformar, factores con valores altos dominarían el resultado.  
- Objetivo: llevarlos a **escala común 1–100**, reservando **0 para exclusiones**.  

---

### 1.2.2 Métodos de normalización

#### 1.2.2.1 Normalización lineal min–max (1–100)

- Fórmula:  
Ni =  (Xi - Xmin) / (Xmax - Xmin) * 100

- Rango resultante: **1–100**.  
- Útil en factores continuos.  

**Ejemplo:**  
- Raster de pendiente: 0–30%.  
- 0% → 1, 15% → 50, 30% → 100.  

---

#### 1.2.2.2 Reclassificación por rangos

- Se definen intervalos con valores de 1–100.  
- Útil para factores cualitativos o discretos.  

**Ejemplo:** Distancia a carreteras  
- 0–200 m → 100 (muy apto)  
- 200–500 m → 75  
- 500–1000 m → 50  
- >1000 m → 25  

**Aplicación en QGIS:**  
- **Raster → Analysis → Reclassify by table**  

---

#### 1.2.2.3 Normalización relativa (z-score escalado a 1–100)

- Fórmula z-score. Estandariza los valores según la media y dispersión: 

Zi = (Xi - μ) / σ

Zi​ = Valor normalizado (z-score)
Xi​ = Valor original
μ = Es el promedio de todos los 
σ = Desviación estándar

- Luego se reescala a 1–100:  
Ni = (Zi - Zmin) / (Zmax - Zmin) * 100

- Útil para datos con distribuciones muy distintas.  

---


### 1.2.3 Comparación de métodos

| Método              | Ventajas                          | Limitaciones                       | Uso recomendado                           |
|---------------------|-----------------------------------|-----------------------------------|-------------------------------------------|
| Min-max (1–100)     | Simple, interpretable             | Sensible a outliers                | Factores continuos con rango acotado      |
| Reclassificación    | Control total por categorías      | Pérdida de detalle                 | Variables cualitativas o discretas        |
| Z-score escalado    | Comparación estadística robusta   | Complejo, requiere reescalado      | Factores con distribuciones diferentes    |


---

## 1.3 Establecimiento de pesos (ponderación)

### 1.3.1 Concepto

- No todos los factores pesan igual.  
- La ponderación multiplica cada raster normalizado por su **peso relativo**.  

---

### 1.3.2 Métodos

1. **Lineales o porcentuales**  
 - Suman 100%.  
 - Ejemplo: Pendiente 50%, Carreteras 30%, Suelo 20%.  

2. **AHP (Analytic Hierarchy Process)**  
 - Comparación pareada entre factores.  
 - Obtención de pesos matemáticamente consistentes.  

---

### 1.3.3 Aplicación en QGIS

- Usar **Raster Calculator**:  

("pendiente_norm" * 0.5) + ("carretera_norm" * 0.3) + ("suelo_norm" * 0.2)

- Resultado: **mapa de aptitud 1–100**, con exclusiones en 0.  

---

