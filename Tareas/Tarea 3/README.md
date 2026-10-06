# Tarea 3 — Notebook de regresión

## Descripción

Este tarea  analiza el funcionamiento de la **regresión lineal** en dos tipos de problemas: regresión y clasificación. Para ello se utiliza el dataset **Wine Quality – Red Wine**, disponible en el UCI Machine Learning Repository.

El dataset contiene 1,599 muestras de vino tinto descritas mediante 11 características fisicoquímicas, como acidez, pH, densidad, sulfatos y porcentaje de alcohol. Además, incluye la variable `quality`, que representa la calidad del vino de acuerdo con evaluaciones sensoriales.

El objetivo principal de la tarea es comparar el comportamiento de la regresión lineal cuando se utiliza para predecir directamente la calidad del vino y cuando se adapta a un problema de clasificación. 

## Contenido del análisis

### Regresión

Se utiliza `quality` como variable objetivo y las 11 características fisicoquímicas como variables predictoras.
Los datos se dividen en:
- 80 % para entrenamiento.
- 20 % para prueba.
- `random_state=42`

### Clasificación
Para convertir el problema en una tarea de clasificación se crea una variable binaria:

- `0` — No bueno: `quality < 7`
- `1` — Bueno: `quality >= 7`

Se ajusta nuevamente una regresión lineal y se utiliza un umbral de **0.5**

## Requisitos

El proyecto fue desarrollado en Python y requiere las siguientes bibliotecas:

- Python 3
- pandas
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook

Las dependencias pueden instalarse con:

pip install pandas numpy matplotlib scikit-learn jupyter

## Ejecución

1. Descargar o clonar los archivos de la tarea.
2. Colocar `winequality-red.csv` en la misma carpeta que `Tarea 3.ipynb`.
3. Abrir el notebook utilizando Jupyter Notebook o JupyterLab.
4. Ejecutar las celdas en orden desde el inicio.

### Declaración de uso de IA
Para el desarrollo de esta práctica se utilizó ChatGPT (OpenAI) como herramienta de apoyo para mejorar la redacción y para orientar algunos procedimientos de análisis y preprocesamiento de datos. Los resultados, el código y las interpretaciones obtenidas fueron revisados y ajustados antes de su incorporación a la tarea. 