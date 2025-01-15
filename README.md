# Clasificación Multiclase y Optimización de Modelos en el Dataset "20 Newsgroups"

Este repositorio contiene ejercicios y experimentos sobre clasificación multiclase, aplicados al dataset "20 Newsgroups". Se presentan las métricas utilizadas en este tipo de problemas y una comparación de varios clasificadores entrenados y optimizados para lograr el mejor rendimiento posible.

<br>

## Ejercicio 1: Interpretación de métricas en clasificación multiclase

En la clasificación multiclase, métricas como **Accuracy**, **Precision**, **Recall** y **F1-Score** se interpretan con ciertas adaptaciones para manejar múltiples clases. En este repositorio, se discuten:

- **Accuracy**: Proporción global de predicciones correctas.
- **Precision, Recall y F1-Score por clase**: Evaluación específica para cada clase.
- **Promedios globales (Micro, Macro, Weighted)**: Resumen general de métricas para evaluar el modelo globalmente.

El enfoque empleado incluye:
1. Reportar métricas por clase.
2. Proporcionar promedios globales utilizando estrategias como micro, macro y weighted.

Consulta la documentación en el archivo para más detalles.

<br>

## Ejercicio 2: Clasificación del dataset "20 Newsgroups"

### Descripción del problema

Se clasifica el dataset "20 Newsgroups" utilizando múltiples clasificadores:
- **Multinomial Naive Bayes**
- **Regresión Logística**
- **LinearSVC**
- **Perceptron**

Se realizan ajustes de hiperparámetros y optimización de cada modelo con el objetivo de encontrar la mejor solución. El rendimiento se evalúa en términos de métricas estándar y visualizaciones de resultados.

### Dataset

- **Fuente**: `sklearn.datasets.fetch_20newsgroups`
- **Clases**: 20 categorías de noticias.
- **Tamaño del conjunto de datos**: 
  - Entrenamiento: ~11,000 documentos.
  - Prueba: ~7,500 documentos.

<br>

## Resultados

### Comparación de modelos

| Modelo               | Accuracy | Principales Hiperparámetros                          |
|----------------------|----------|-----------------------------------------------------|
| **LinearSVC**        | 0.823    | `C=0.01, loss='squared_hinge', max_iter=15000`     |
| **LogisticRegression** | 0.803 | `C=1, penalty='l2', solver='lbfgs'`                 |
| **MultinomialNB**    | 0.792    | `alpha=0.0001, fit_prior=True`                     |
| **Perceptron**       | 0.741    | `alpha=0.0001`                                     |

### Mejor solución: LinearSVC
- **Accuracy**: 82.3%
- **Principales métricas por clase**:  
  - Promedio ponderado de F1-Score: 0.822.
  - Mejores clases: 
    - *rec.motorcycles*: F1-Score = 0.942.
    - *rec.sport.hockey*: F1-Score = 0.944.
  - Clases más difíciles: 
    - *talk.religion.misc*: F1-Score = 0.650.
    - *talk.politics.misc*: F1-Score = 0.667.

<br>

## Visualizaciones

El repositorio incluye scripts para generar gráficos de **Precision**, **Recall**, **F1-Score** y **Support** para cada clase. Los gráficos proporcionan una visión clara del rendimiento del modelo por categoría y a nivel global.

<br>

## Requisitos

- Python >= 3.7
- Librerías principales:
  - `scikit-learn`
  - `pandas`
  - `matplotlib`

--- 

¡Espero que sea útil! Si necesitas ajustes, no dudes en pedírmelo. 😊
