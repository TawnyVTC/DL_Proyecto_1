
# Predicción de Default en Préstamos de Lending Club

## Introducción

El auge de las plataformas de préstamos peer-to-peer, como **Lending Club**, ha generado grandes volúmenes de datos relacionados con las solicitudes, aprobaciones y desempeño de créditos. Una de las principales preocupaciones para estas entidades es estimar el riesgo de incumplimiento (default) de los solicitantes, con el fin de minimizar pérdidas y optimizar la toma de decisiones.

En este proyecto se busca construir un modelo de **clasificación supervisada** que prediga si un préstamo:

* Será **pagado completamente** (`default = 0`)
* O resultará en **incumplimiento** (`default = 1`)

A partir de variables financieras y demográficas de los prestatarios.

## Objetivos

1. **Preprocesar y explorar los datos** de Lending Club, entendiendo la distribución de variables relevantes, valores nulos y relaciones entre ellas.
2. **Crear la variable objetivo `default`** a partir de la columna `loan_status`, diferenciando entre préstamos exitosos y en incumplimiento.
3. **Entrenar y evaluar modelos de clasificación** utilizando un **Multilayer Perceptron (MLP)** bajo dos enfoques:

   * **Scikit-learn (Python puro)**
   * **PySpark (big data y procesamiento distribuido)**
4. **Comparar el desempeño** entre ambas implementaciones en términos de:

   * Exactitud (Accuracy)
   * Precisión (Precision)
   * Sensibilidad (Recall)
   * Puntaje F1
   * Área bajo la curva ROC (AUC-ROC)
   * Matriz de confusión
5. **Aplicar LIME (Local Interpretable Model-Agnostic Explanations)** para interpretar predicciones individuales y obtener explicaciones comprensibles sobre la contribución de cada variable en las decisiones del modelo.

## Metodología

* **Preprocesamiento**:

  * Codificación de variables categóricas (`OneHotEncoder`, `StringIndexer`)
  * Escalado de variables numéricas (`StandardScaler`)
  * Manejo de valores nulos
* **División de datos** en entrenamiento (80%) y prueba (20%), estratificada por clase.
* **Modelado con MLP**:

  * Búsqueda de hiperparámetros (capas ocultas, tasa de regularización `alpha`, número de iteraciones).
  * Entrenamiento y evaluación en ambos entornos (scikit-learn y PySpark).
* **Interpretabilidad con LIME**: explicación de predicciones individuales para comprender el impacto de las variables.

## Resultados esperados

* Un modelo capaz de **distinguir patrones de riesgo crediticio** en grandes volúmenes de datos.
* Comparación entre un flujo tradicional con scikit-learn y un enfoque distribuido con PySpark, resaltando ventajas y limitaciones de cada uno.
* Explicaciones locales que permitan a analistas y tomadores de decisiones **confiar en las predicciones** del modelo al entender qué variables influyen en cada resultado.

