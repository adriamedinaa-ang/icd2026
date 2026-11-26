## Predicción de toxicidad de nanopartículas mediante aprendizaje automático
Proyecto final de ciencia de datos enfocado en la clasificación de nanopartículas de óxidos metálicos como tóxicas o no tóxicas a partir de sus propiedades fisicoquímicas y condiciones experimentales.
### Descripción
Los ensayos experimentales de toxicidad pueden requerir tiempos prolongados, reactivos y recursos especializados. El aprendizaje automático ofrece la posibilidad de aprovechar los datos obtenidos durante la caracterización de nanopartículas, junto con las condiciones de exposición, para orientar evaluaciones preliminares de toxicidad sin sustituir la validación experimental.
Preguntas de investigación
1. ¿Qué tan efectivos son los modelos de aprendizaje automático para predecir la toxicidad de nanopartículas de óxidos metálicos?
2. ¿Cómo influyen las técnicas de selección y reducción de características en el desempeño predictivo?
3. ¿Cómo afectan los registros duplicados, las etiquetas contradictorias y las técnicas de balanceo al desempeño de los clasificadores?
4. ¿Qué capacidad tienen los modelos para generalizar a tipos de nanopartículas no vistos durante el entrenamiento?
#### Conjunto de datos
Se utiliza el Nanoparticle Toxicity Dataset, publicado en Kaggle por UCI Machine Learning.
- 881 observaciones y 10 variables predictoras (9 numéricas y 1 categórica).
- Cinco tipos de nanopartículas: ZnO, TiO₂, CuO, Al₂O₃ y Fe₂O₃.
- Variable objetivo: class (Toxic y nonToxic).
#### Metodología
1. Análisis exploratorio y diagnóstico de calidad de datos.
2. Comparación de cuatro tratamientos: datos originales, sin contradicciones, sin duplicados y sin duplicados ni contradicciones.
3. Validación cruzada estratificada por grupos de cinco pliegues, evitando compartir grupos entre entrenamiento y evaluación.
4. Comparación de tres representaciones: sin reducción, PCA (95 % de varianza explicada) y selección mediante Mutual Information.
5. Evaluación de estrategias sin balanceo, Random Oversampling y SMOTE-NC, según el tratamiento de datos. El tratamiento y balanceo se aplican dentro del entrenamiento.
6. Comparación de seis clasificadores: regresión logística, árbol de decisión, SVM, Random Forest, XGBoost y MLP.
7. Optimización de SVM, Random Forest y XGBoost mediante búsqueda aleatoria y refinamiento por cuadrícula.
8. Validación cruzada anidada (cinco pliegues externos y tres internos) y análisis de matrices de confusión, coincidencia y persistencia de errores.
9. Evaluación exploratoria Leave-One-Nanoparticle-Type-Out, excluyendo la identidad del material de los predictores.
La métrica principal es el F1-score de la clase tóxica, complementada con precisión, sensibilidad, especificidad y exactitud.
#### Requisitos y ejecución
El notebook registra Python 3.13.0 como versión del entorno. Se requieren Jupyter y las bibliotecas indicadas a continuación.
python -m pip install notebook pandas numpy matplotlib matplotlib-venn seaborn scikit-learn imbalanced-learn xgboost scipy tqdm
1. Descargar el conjunto de datos desde Kaggle.
2. Colocar el CSV con el nombre nanotox_dataset.csv en el mismo directorio que el notebook.
3. Iniciar Jupyter con jupyter notebook y abrir el notebook.
4. Ejecutar las celdas en orden. Las búsquedas de hiperparámetros y la validación anidada pueden requerir tiempo considerable

#### Referencias y uso de IA
Las referencias bibliográficas se encuentran al final del notebook. Se utilizó ChatGPT (OpenAI) como herramienta de apoyo; el código, los resultados y las interpretaciones fueron revisados y ajustados antes de su incorporación al proyecto.