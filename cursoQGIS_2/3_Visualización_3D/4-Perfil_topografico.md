## 🏔️ Crear perfiles topográficos con QGIS (herramienta integrada)

QGIS permite generar **perfiles topográficos** de manera sencilla, tanto con **plugins externos** como con su **herramienta nativa**.  
En este apartado veremos cómo hacerlo **usando la herramienta integrada de QGIS**.

---

### Opciones disponibles

Existen dos formas principales de crear perfiles de elevación en QGIS:

1. Usar complementos como **qProf**, **VoGIS-ProfilTool** o **Profile Tool**.  
2. Utilizar la **herramienta integrada** que viene con QGIS a partir de versiones recientes.

A continuación, nos centraremos en esta segunda opción.

---

### Paso 1. Activar el panel de perfil de elevación

1. En el menú superior, ve a: Ver-Perfil de Elevación


2. Se abrirá el panel **Perfil de elevación**, que utilizaremos para generar el gráfico topográfico.

---

###  Paso 2. Configurar las propiedades de elevación de la capa

1. Haz **doble clic** sobre la capa que contiene la información altimétrica (por ejemplo, un MDT).  
2. En la ventana de **Propiedades de capa**, accede a la pestaña **Elevation**.

---

### Representación de la superficie de elevación

- Activa la casilla **“Representar superficie de elevación”**.  
- Desde esta sección podrás:
- Ajustar el **factor de escala (Scale)** para exagerar la altura o compensar diferencias de unidades.  
- Aplicar un **desplazamiento vertical (Offset)** si es necesario.

Esto te permitirá controlar cómo se representarán las elevaciones en el perfil.

---

### Definir la representación del perfil

En la parte inferior de la pestaña **Elevation**, puedes decidir cómo visualizar el perfil:

- Como **línea** (solo contorno), o  
- Como **polígono** (relleno).

Ambos modos permiten personalizar la **simbología** (color, grosor, estilo, transparencia, etc.) según tus preferencias.

---

### Paso 3. Crear el perfil topográfico

1. Una vez configurada la capa de elevación, vuelve al panel **Perfil de elevación**.  
2. Verás tu MDT disponible en la lista desplegable.  
3. Selecciona la herramienta **“Capturar curva”** (*Capture Curve*).  
4. Dibuja una **línea de corte** sobre el terreno, siguiendo el recorrido para el que quieres generar el perfil.

---

### Paso 4. Finalizar el perfil

- Cuando termines de dibujar la línea, haz **clic derecho** para finalizar la digitalización.  
- QGIS generará automáticamente el **perfil topográfico** correspondiente, mostrando las variaciones de altura a lo largo del trazado.

---

