## Práctica 3: Tarea de clasificación
## Descripción

Esta práctica compara cinco algoritmos de aprendizaje automático supervisado para predecir la situación académica final de estudiantes universitarios a partir de la información disponible al cierre del primer semestre. El problema contempla tres clases:

- **Graduate:** estudiantes que lograron graduarse.
- **Dropout:** estudiantes que abandonaron sus estudios.
- **Enrolled:** estudiantes que permanecen inscritos.

Se utiliza una versión dividida en entrenamiento y prueba del conjunto de datos **Predict Students' Dropout and Academic Success**.

## Datasets

El notebook carga los siguientes archivos CSV desde el directorio de ejecución:

- `desercion-entrenamiento.csv`: **3,539** observaciones, con la columna objetivo `Target`.
- `desercion-prueba.csv`: **885** observaciones, sin la columna objetivo.

Para la comparación principal se utilizan **30 características disponibles al finalizar el primer semestre**, excluyendo `id` y `Target`. El entrenamiento también contiene **seis variables académicas del segundo semestre**, utilizadas exclusivamente en un experimento adicional.

## Contenido del notebook

1. **Análisis exploratorio de datos (EDA)** d
2. **Árbol de decisión** 
3. **Naive Bayes:** comparación de `GaussianNB` y `CategoricalNB`
4. **k vecinos más cercanos (kNN)** 
5. **Máquinas de soporte vectorial (SVM):** comparación de kernels lineal, RBF y polinomial
6. **Regresión logística**
7. **Comparación general:** F1 macro, desviación estándar, tiempos de búsqueda, métricas por clase y matrices de confusión.
8. **Impacto del segundo semestre**
9. **Entrenamiento final** 
10. **Conclusiones y referencias**

## Metodología

- **Validación cruzada:** `StratifiedKFold(n_splits=5, shuffle=True, random_state=42)`. Se reutilizan las mismas particiones en la comparación de los clasificadores.
- **Optimización:** `RandomizedSearchCV`, con **F1 macro** como métrica principal.
- **Preprocesamiento:** pipelines con imputación, codificación categórica, escalado o discretización según el algoritmo. Las transformaciones se ajustan dentro de la validación cruzada.
- **Evaluación:** promedio y desviación estándar de F1 macro, exactitud, sensibilidad y especificidad por clase, tiempos de búsqueda y gráficas de convergencia.


## Archivos y ejecución

Los archivos deben estar disponibles en el directorio desde el que se ejecuta el notebook:

```text
.
├── Practice 3.ipynb
├── desercion-entrenamiento.csv
├── desercion-prueba.csv
├── README.md
└── predicciones_finales.csv       # Se genera al ejecutar el notebook
```

### Dependencias

- Python 3
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `scipy`
- Jupyter Notebook o JupyterLab (para ejecutar el `.ipynb`)

### Pasos para reproducir

1. Colocar `Practice 3.ipynb` y los dos archivos CSV en el mismo directorio de ejecución.
2. Instalar las dependencias en el entorno de Python correspondiente.
3. Abrir el notebook en Jupyter Notebook o JupyterLab.
4. Ejecutar las celdas en orden.
5. Revisar las métricas, gráficas y comparaciones de los clasificadores.
6. Verificar la generación de `predicciones_finales.csv`.

## Referencia principal

Realinho, V., Vieira Martins, M., Machado, J., & Baptista, L. (2021). *Predict Students' Dropout and Academic Success* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5MC89

### Declaración de uso de IA
Para el desarrollo de esta práctica se utilizó ChatGPT (OpenAI) como herramienta de apoyo. Los resultados, el código y las interpretaciones obtenidas fueron revisados y ajustados antes de su incorporación a la práctica. 
