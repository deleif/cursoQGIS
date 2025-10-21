## Plugin QGIS2threejs

El **plugin QGIS2threejs** es una extensión clásica de QGIS que permite **exportar proyectos a un entorno web interactivo en 3D**.  
Con él, puedes generar visualizaciones tridimensionales directamente desde tus capas (raster y vectoriales) y ver el resultado en cualquier navegador web, sin necesidad de software adicional.

Aunque las versiones más recientes de QGIS incluyen su propia **vista 3D nativa**, QGIS2threejs sigue siendo una herramienta muy útil para **crear escenas exportables y compartibles fácilmente**, por ejemplo en presentaciones, webs o informes.

https://github.com/minorua/Qgis2threejs?tab=readme-ov-file

---

### 🌍 ¿Qué permite hacer QGIS2threejs?

Con este complemento puedes:

- Representar **Modelos Digitales de Elevación (MDE/DEM)** en 3D.  
- Superponer **capas vectoriales** (puntos, líneas y polígonos) sobre el terreno.  
- Aplicar **texturas, colores y transparencias** personalizadas.  
- Controlar la **escala vertical**, la iluminación y la posición de la cámara.  
- Exportar la escena 3D a un archivo **HTML interactivo** para compartirlo fácilmente.

---

### ⚙️ Instalación del plugin

1. En QGIS, abre el menú **Complementos → Administrar e instalar complementos...**  
2. Busca **QGIS2threejs**.  
3. Haz clic en **Instalar complemento**.  
4. Una vez instalado, aparecerá un nuevo icono en la barra de herramientas o en el menú **Web → QGIS2threejs → Exportar**.

---

### 🗺️ Crear una escena 3D

1. Carga un **Modelo Digital de Elevación (DEM)** en tu proyecto QGIS.  
2. Añade las capas vectoriales que desees incluir (por ejemplo, edificios, carreteras o puntos de observación).  
3. Abre el plugin desde:  
   **Web → QGIS2threejs → Exportar a página web 3D**.  
4. En la ventana de configuración:
   - Selecciona el **DEM** como superficie base.  
   - Elige las capas vectoriales que quieras mostrar.  
   - Ajusta la **exageración vertical**, la **textura**, y la **altura de los objetos**.  
5. Pulsa **Exportar** y guarda el resultado en una carpeta.

El complemento generará un archivo `index.html` junto con una serie de archivos asociados (texturas, datos, scripts).  
Abre el archivo HTML en tu navegador y podrás **moverte libremente por el terreno en 3D**.

---

### Añadir un shp

- Pulsa con el botón derecho sobre la capa shp y selecciona Properties. 

- Configura los siguientes parámetros: Object type > Extruded y en altitud poner el valor=2. En Style modificamos el parámetro Height por el campo de población. La extrusión es el proceso de estirar una forma plana 2D a un objeto 3D

---


### 💡  Consejos

- Si tu DEM es muy detallado, usa una **resolución menor** para que el modelo cargue más rápido. 

- Guarda tu configuración con el botón **Guardar plantilla** si vas a crear varias escenas con el mismo estilo.  
- Si las capas aparecen demasiado bajas o altas, ajusta la **exageración vertical** y el **offset (desplazamiento)**.

---

### 📦 Exportar y compartir

El resultado de QGIS2threejs es una carpeta web que contiene todos los archivos necesarios para visualizar la escena.  
Puedes:

- Abrir el archivo `index.html` localmente en cualquier navegador.  
- Subir la carpeta a un servidor web o a una plataforma como GitHub Pages para **compartir el modelo 3D online**.  

---

### 🔗 Recursos

- [Manual QGIS2threejs (GitHub oficial)](https://github.com/minorua/Qgis2threejs)  
- [Manual QGIS](https://docs.qgis.org/3.40/es/docs/user_manual/map_views/3d_map_view.html)

---

En resumen, **QGIS2threejs** es una herramienta sencilla y potente para **convertir tus mapas en experiencias 3D interactivas**, ideales para mostrar resultados de análisis o difundir información geográfica de forma visual y atractiva.
