# **Segmentación de granos de café usando visión por computador**

### Descripción
La imagen contiene granos de café en diferentes etapas de maduración. La tarea consiste en desarrollar un cuaderno interactivo en Python que realice la segmentación de cada grano y muestre los pasos seguidos para lograr la separación de granos que están pegados.

### Pasos

1. **Configuración del Entorno:**
   - **Crea un archivo `requirements.txt`**:
     - Instala las dependencias necesarias (por ejemplo, `opencv-python`, `numpy`, `scipy`) en un entorno virtual.
     - Genera el archivo `requirements.txt` ejecutando:
       ```bash
       pip freeze > requirements.txt
       ```
     - Este archivo debe estar incluido en el repositorio para que otros usuarios puedan instalar fácilmente las dependencias ejecutando:
       ```bash
       pip install -r requirements.txt
       ```

2. **Cargar la Imagen:**
   - Usa OpenCV (`cv2.imread`) para cargar la imagen en el cuaderno y conviértela a escala de grises.
   - Muestra la imagen cargada.

3. **Preprocesamiento de la Imagen:**
   - Binariza la imagen separando los granos del fondo. Usa filtros de suavizado si es necesario.
   - Explica cada paso brevemente en una celda de texto para que el proceso sea claro.

5. **Operaciones Morfológicas:**
   - Aplica operaciones morfológicas como dilatación y erosión (también conocidas como apertura y cierre) para eliminar imperfecciones y mejorar la separación de los granos pegados.
   - Utiliza la transformación de distancia (`cv2.distanceTransform`) para obtener una "imagen de distancia", que será útil en el siguiente paso de segmentación.
   - Muestra la imagen en cada etapa para ver cómo evolucionan las modificaciones.

6. **Algoritmo Watershed:**
   - Crea marcadores basados en la imagen de distancia para indicar las áreas de cada grano.
   - Usa el algoritmo Watershed (`cv2.watershed`) de OpenCV para separar los granos pegados, definiendo límites claros entre cada grano.
   - Explica brevemente el funcionamiento del algoritmo Watershed y muestra la imagen con los granos segmentados.

7. **Detección de Componentes Conectadas:**
   - Utiliza `scipy.ndimage.label` o `cv2.connectedComponents` para identificar componentes conectadas en la imagen segmentada.
   - Asegúrate de que cada grano esté identificado como una componente individual y muestra el resultado en la imagen final.

8. **Documentación en el Cuaderno:**
   - En cada paso, incluye celdas de texto para describir brevemente qué hace cada bloque de código y por qué es necesario.
   - Al final del cuaderno, incluye una breve conclusión sobre los resultados de la segmentación y las dificultades encontradas.

### Entrega

- **Archivos a Entregar:**
  - Un archivo `segmentacion_cafe.ipynb` (cuaderno interactivo) con todo el proceso documentado y visualizado.
  - Un archivo `requirements.txt` con las dependencias necesarias para ejecutar el proyecto.
  

### Criterios de Evaluación
- **Calidad de la segmentación y separación de los granos.**
- **Explicación clara en el cuaderno interactivo, con visualización paso a paso.**

## **Recursos**

- [Image Segmentation with Watershed Algorithm](https://docs.opencv.org/4.x/d3/db4/tutorial_py_watershed.html)
