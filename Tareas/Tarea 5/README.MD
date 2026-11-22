# Tarea 5 — Redes neuronales convolucionales (CNN)

## Descripción

Esta tarea tiene como objetivo diseñar y evaluar una red neuronal convolucional (CNN) utilizando el conjunto de datos MNIST, compuesto por imágenes de dígitos manuscritos del 0 al 9.

El objetivo principal es desarrollar una arquitectura con *Global Average Pooling* (GAP) que alcance una exactitud de validación superior al 95%, utilizando menos parámetros entrenables que una CNN de referencia con *Flatten*.

Para ello, se comparan ambas arquitecturas y se exploran 19 variantes con GAP, modificando el número de capas convolucionales, los filtros y la distribución de las operaciones de *pooling*. Posteriormente, se evalúa la robustez de los modelos frente a desplazamientos de 0, 2 y 4 píxeles.

Como resultado, se seleccionó GAP 19, que alcanzó una exactitud de validación del 95.40 % con 9 754 parámetros entrenables, lo que representa una reducción del 82.05 % respecto al modelo con Flatten.

## Requisitos

El proyecto fue desarrollado en Python y requiere las siguientes bibliotecas:

- Python 3
- NumPy
- pandas
- Matplotlib
- scikit-learn
- TensorFlow / Keras
- Jupyter Notebook

Las dependencias pueden instalarse con:
pip install numpy pandas matplotlib scikit-learn tensorflow jupyter

## Ejecución

1. Descargar o clonar los archivos de la tarea.
2. Abrir `Tarea 5.ipynb` utilizando Jupyter Notebook o JupyterLab.
3. Ejecutar las celdas en orden desde el inicio.
4. El conjunto de datos MNIST se descargará automáticamente mediante Keras si no está disponible localmente.

El notebook incluye el entrenamiento de los modelos de referencia, la exploración de arquitecturas GAP y la evaluación de robustez ante desplazamientos.

### Declaración de uso de IA

Para el desarrollo de esta tarea se utilizó ChatGPT (OpenAI) como herramienta de apoyo. Los resultados, el código y las interpretaciones obtenidas fueron revisados y ajustados antes de su incorporación a la tarea.