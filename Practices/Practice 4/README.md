# Práctica 4 — Métodos de ensamble para clasificación

## Descripción

Esta práctica tiene como objetivo evaluar y comparar diferentes algoritmos de clasificación y métodos de ensamble utilizando dos conjuntos de datos con características distintas.

Se analizan clasificadores individuales y técnicas de **Bagging, Boosting, Voting y Stacking**, además de estrategias para manejar el desbalance de clases y optimizar hiperparámetros.

Los modelos se evalúan mediante validación cruzada estratificada de cinco pliegues, utilizando como métrica principal el **F1-macro**, junto con la sensibilidad de las clases de interés y el tiempo de entrenamiento.

## Conjuntos de datos

### Parte 1. Predict Students' Dropout and Academic Success

**Fuente:** UCI Machine Learning Repository.

**Enlace:** https://doi.org/10.24432/C5MC89

Este conjunto de datos contiene información académica y sociodemográfica de estudiantes universitarios, con el objetivo de predecir su situación académica.

La variable objetivo contiene tres categorías:

- `Dropout`: estudiantes que abandonaron sus estudios.
- `Enrolled`: estudiantes que continúan inscritos.
- `Graduate`: estudiantes que finalizaron sus estudios.

El problema corresponde a una clasificación multiclase y presenta desbalance entre las categorías, especialmente en la clase `Enrolled`.

### Parte 2. Bank Marketing

**Fuente:** UCI Machine Learning Repository.

**Enlace:** https://doi.org/10.24432/C5K306

Este conjunto de datos contiene información de campañas de marketing telefónico realizadas por una institución bancaria portuguesa. El objetivo es predecir si un cliente contratará un depósito a plazo.

Se utilizaron **41,188 registros** y la variable objetivo `y`, con dos categorías:

- `no` (0): el cliente no contrató el depósito.
- `yes` (1): el cliente contrató el depósito.

Se eliminó la variable `duration`, ya que representa la duración de la llamada y no estaría disponible antes de realizarla. Con esto se evita utilizar información que no podría conocerse al momento de efectuar la predicción.

El conjunto presenta un desbalance importante, debido a que aproximadamente el 11.3 % de los registros pertenecen a la clase `yes`.

## Metodología

En ambos conjuntos de datos se implementaron las siguientes estrategias:

1. **Clasificadores individuales:** Árbol de decisión, Naive Bayes, kNN, SVM y regresión logística.
2. **Bagging:** Bagging Classifier, Random Forest y Extra-Trees.
3. **Boosting:** AdaBoost, XGBoost y LightGBM.
4. **Combinación de clasificadores:** Voting duro, Voting suave y Stacking.
5. **Optimización de hiperparámetros:** Evaluación de 50 configuraciones para Random Forest, XGBoost y LightGBM.
6. **Manejo del desbalance:** Ponderación de clases y técnicas de sobremuestreo, según el conjunto de datos.

El preprocesamiento y las estrategias de remuestreo se integraron dentro de los pipelines correspondientes para evitar fugas de información entre los pliegues de validación.

### Evaluación

Se utilizó validación cruzada estratificada de cinco pliegues y se analizaron las siguientes métricas:

- **F1-macro:** métrica principal para comparar el desempeño entre clases.
- **Sensibilidad:** capacidad para identificar correctamente la clase de interés.
- **Tiempo de entrenamiento:** costo computacional de los modelos.
- **Matriz de confusión:** análisis de los errores de clasificación.

## Requisitos

Para ejecutar el proyecto se necesita:

- Python 3.
- Jupyter Notebook o JupyterLab.
- NumPy.
- Pandas.
- Matplotlib.
- Scikit-learn.
- Imbalanced-learn.
- XGBoost.
- LightGBM.
- Joblib.
- SciPy.

## Ejecución del notebook

1. Descargar o clonar el repositorio.
2. Instalar las dependencias.
3. Verificar que los conjuntos de datos se encuentren en la carpeta.
4. Abrir `Practice 4.ipynb` en Jupyter Notebook o JupyterLab.
5. Seleccionar **Kernel → Restart & Run All** para ejecutar todas las celdas desde el inicio.


## Modelos guardados

Se incluyen dos modelos entrenados mediante `joblib`:

- `Adria-LightGBM-P1.joblib`: modelo seleccionado para la predicción de deserción estudiantil.
- `Adria-RandomForest-P2.joblib`: modelo seleccionado para Bank Marketing.

Los modelos se entrenan utilizando los datos disponibles de sus respectivos conjuntos, después de seleccionar sus configuraciones.

## Referencias

Realinho, V., Vieira Martins, M., Machado, J., & Baptista, L. (2021). *Predict Students' Dropout and Academic Success* [Conjunto de datos]. UCI Machine Learning Repository. https://doi.org/10.24432/C5MC89

Moro, S., Rita, P., & Cortez, P. (2014). *Bank Marketing* [Conjunto de datos]. UCI Machine Learning Repository. https://doi.org/10.24432/C5K306

### Declaración de uso de IA

Para el desarrollo de esta práctica se utilizó ChatGPT (OpenAI) como herramienta de apoyo. Los resultados, el código y las interpretaciones obtenidas fueron revisados y ajustados antes de su incorporación a la práctica. 
