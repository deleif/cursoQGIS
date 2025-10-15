# 2. Construcción de un MCE completo – 1h

## Objetivos específicos

- Integrar factores normalizados y aplicar restricciones para generar un mapa de idoneidad.  
- Aplicar ponderaciones a los factores y evaluar el impacto en los resultados.  
- Visualizar e interpretar mapas finales de aptitud.  
- Evaluar la sensibilidad del modelo ante cambios en las ponderaciones.  

---

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

- Cada factor puede tener diferente importancia relativa en la decisión.  
- Los pesos reflejan esta importancia y modifican el resultado final del mapa de aptitud.  

### Métodos

- **Escalas lineales o porcentuales**: asignar valores entre 0 y 1 o porcentajes que sumen 1 o 100.  
- **Método AHP**: justificación sistemática de pesos mediante comparaciones pareadas.  

### Herramientas en QGIS

- **Raster Calculator**: multiplicar cada factor normalizado por su peso y sumar.  
- Ejemplo:  
