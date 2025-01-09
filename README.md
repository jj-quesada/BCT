<h2>Basketball Court Tracker - BCT</h2>

**Autores:** Óscar Muñoz Hidalgo y Juan José Quesada Acosta

---

Basketball Court Tracker - BCT - es una propuesta de sistema de visión por computador para la detección y análisis de zonas y jugadores de partidos de baloncesto, con la funcionalidad automatizada para generar homografías del estado del partido a partir de una única fuente de imagen “estándar” y transformarla en un diagrama de la vista cenital calculada inspirado por videojuegos como FIFA.

![FIFA](./assets/README_images/FIFA.gif)

Mediante el uso de diferentes modelos de detección y segmentación, así como algunas técnicas de tratamiento de imágenes y heurísticas propias, hemos desarrollado un primer prototipo funcional con ciertas limitaciones técnicas. 

---

<h3>Entorno de Python para la ejecución</h3>

Se recomienda crear un entorno de Anaconda que incluya los siguiente paquetes:

- OpenCV
- NumPy
- Ultralytics
- Scikit Learn
- Scikit Image

Para ello, puede lanzar las siguientes líneas en una terminal:

```
conda create --name BCT python=3.12.1
conda activate BCT

pip install opencv-python numpy ultralytics scikit-learn scikit-image
```

---

<h3>Estructura del proyecto</h3>

```
├── assets
│   ├── court_diagrams       # Diagramas de la cancha
│   ├── README_images        # Imágenes para el README
│   └── videos               # Videos de prueba
├── functionality_test_notebooks
│   ├── detection-and-tracking.ipynb  # Cuaderno para detección y seguimiento
│   └── homography.ipynb              # Cuaderno para cálculo de homografía
├── output                  # Carpeta para guardar los videos resultantes
├── training_results
│   ├── detection
│   │   ├── ballhandler     # Resultados del modelo de detección "ballhandler"
│   │   └── bpdv1           # Resultados del modelo de detección "bpdv1"
│   └── segmentation
│       ├── segmentv1       # Resultados del modelo de segmentación versión 1
│       └── segmentv2       # Resultados del modelo de segmentación versión 2
├── yolo_models
│   ├── detection           # Modelos YOLO para detección
│   ├── segmentation        # Modelos YOLO para segmentación
│   └── base_models         # Modelos base de YOLO
└── BCT.ipynb               # Cuaderno principal del proyecto
```

---

<h3>Ejecución del proyecto</h3>

Para ejecutar el proyecto, diríjase al cuaderno **BCT.ipynb** y ejecute todas las celdas en orden.

Puede modificar el vídeo usada por el programa cambiando la ruta en la variable **video_path**. Hay 5 vídeos de ejemplo en */assets/videos*.

Tambien puede cambiar el diagrama por uno en fondo negro con líneas blancas cambiando la ruta en la variable **diagram**. Su ruta es */assets/court_diagrams/black_court.png*.

Al **ejecutar el programa se abrirán 2 ventanas**:
- Una con el vídeo donde se realizan las **detecciones, posicionamiento y asignación de equipos**.
- Otra con el **diagrama y la representación** de los jugadores y árbitros.


El procesamiento de los fotogramas, al menos en nuestros equipos, **no es a tiempo real**.


---

<h3>Resultados tras la ejecución</h3>

El resultado de la ejecución se alojará en la carpeta */output*, donde se creará una subcarpeta por cada ejecución con el siguiente formato: */output/{video_name}_{current_time}*. 

En su interior se generan 4 vídeos:
- Dos vídeos de la detección y asignación de equipos, uno a velocidad normal y otro a x0.5.
- Dos vídeos de la representación en el diagrama, uno a velocidad normal y otro a x0.5.

---

<h3>Ejemplos de la ejecución</h3>

- [Vídeo procesado de la detección](https://alumnosulpgc-my.sharepoint.com/:v:/g/personal/juan_quesada108_alu_ulpgc_es/Ec17HcCaRFFEiXI5j8nFEQUBWuv0VMcx5xK6Y3OX95NlzQ?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=kDwGQk)
- [Diagrama de la representación a 0.5x velocidad](https://alumnosulpgc-my.sharepoint.com/:v:/g/personal/juan_quesada108_alu_ulpgc_es/EdxcDdDCmo5KpUSQr6rkAgoBTyxp12L3xcQ4XTqpHxtr2w?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=KB9i0I)




