### Práctica 1: Análisis exploratorio de dataset
##### Dataset
El archivo utilizado es para el desarollo de la práctica es:
`Diabetes_Mexico.csv`

El dataset contiene 2,549 registros y 24 atributos, correspondientes a información de los participantes.

Las variables incluyen:
- Información demográfica, como edad, sexo y ciudad.
- Mediciones antropométricas, como peso, estatura e IMC.
- Variables bioquímicas, como glucosa, insulina, triglicéridos, colesterol total, HDL y LDL.
- Variables relacionadas con el diseño de la muestra.
- La variable objetivo `riesgo_diabetes_cat`, que clasifica el riesgo de diabetes en tres categorías:
    0: riesgo bajo
    1: riesgo moderado
    2: riesgo alto

#### Contenido del análisis
El notebook incluye:
1. Carga e inspección inicial del dataset.
2. Análisis de la estructura y tipos de datos.
3. Exploración de características demográficas.
4. Análisis de la variable objetivo.
5. Identificación de valores faltantes y valores fuera de rango.
6. Conversión de variables almacenadas con tipos de datos incorrectos.
7. Análisis univariado y bivariado.
8. Análisis multivariado mediante una matriz de correlación.
9. Interpretación de los principales resultados y conclusiones.
#### Requisitos de ejecución
Para ejecutar la práctica se requiere Python 3 y un entorno compatible con Jupyter Notebook.
Las librerías utilizadas son:
- NumPy
- Pandas
- Matplotlib
- Seaborn
#### Intrucciones de uso
1. Descargar o clonar el repositorio.
2. Colocar `Diabetes_Mexico.csv` en la misma carpeta que el notebook.
3. Abrir `Practice 1.ipynb` utilizando Jupyter Notebook, JupyterLab o un entorno compatible.
4. Correr el bloque que instala las dependencias.
5. Ejecutar las celdas en orden, desde la primera hasta la última.