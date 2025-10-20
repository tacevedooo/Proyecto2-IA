# 📘 Proyecto: Clasificación y Agrupamiento usando “Life Style Data”
#### Asignatura: Introducción a la Inteligencia Artificial

## Descripción General
Este proyecto implementa un sistema de análisis de datos y aprendizaje automático sobre el dataset público “Life Style Data” disponible en Kaggle. El objetivo es aplicar y comparar diferentes técnicas de aprendizaje supervisado y no supervisado para tareas de clasificación y agrupamiento de personas según sus características de estilo de vida (edad, género, actividad, etc.).
Se pretende identificar patrones en el estilo de vida y predecir alguna categoría relevante, así como agrupar patrones de comportamiento similares.

## Objetivo General
Desarrollar una aplicación (pipeline) que, a partir de este dataset abierto, implemente y compare diferentes técnicas de aprendizaje de máquinas para clasificación y agrupamiento.

#### Objetivos Específicos
Seleccionar y justificar una variable objetivo adecuada del dataset con al menos 4 clases (o convertirla para tener 4+ clases si es necesario).

Realizar el preprocesamiento del dataset: normalización de variables numéricas, manejo de valores faltantes, tratamiento de outliers y, de ser necesario, balanceo de clases.

Implementar algoritmos supervisados: Árboles de Decisión, K-Vecinos Más Cercanos (KNN), Máquinas de Vectores de Soporte (SVM) y Redes Neuronales (MLP).

Implementar algoritmos no supervisados: K-Means y DBSCAN para detectar grupos o segmentos de estilo de vida.

Evaluar los modelos supervisados mediante métricas de desempeño: accuracy, precisión, recall, F1-score, además de curvas ROC y Precision-Recall si la variable objetivo lo permite.

Evaluar los modelos no supervisados mediante métricas de agrupamiento como Silhouette Score y análisis del codo para K-Means.

Visualizar y analizar los resultados para comparar el comportamiento de los modelos bajo diferentes configuraciones (por ejemplo, con/sin outliers, diferentes escalados, diferentes subconjuntos de variables).

Interpretar los hallazgos: ¿qué patrones de estilo de vida emergen? ¿qué variables son más predictivas? ¿qué segmentos se identifican? ¿qué implicaciones podría tener en un contexto real?

## Estructura del Proyecto

´´´
📦 life-style-project
├── data/
│   ├── life_style_data.csv           # Dataset original
│   ├── subset/                        # Subconjunto de datos usado
│   │   ├── subset_life_style_rowsN_seedXYZ.csv
│   │   ├── metadata.json              # Para reproducibilidad del subconjunto
│   ├── processed/                     # Datasets preprocesados (normalizados, balanceados, etc.)
│
├── notebooks/
│   ├── 1_preprocessing.ipynb          # Limpieza y preparación del dataset
│   ├── 2_supervised_models.ipynb      # Modelos supervisados (Árbol, KNN, SVM, NN)
│   ├── 3_unsupervised_models.ipynb    # Modelos no supervisados (K-Means, DBSCAN)
│   ├── 4_visualizations.ipynb         # Gráficas y análisis de resultados
│
├── results/
│   ├── figures/                        # Gráficas generadas (barras, ROC, silhouette, etc.)
│   ├── tables/                         # Resultados en formato CSV/tables
│
├── README.md                           # Descripción general del proyecto
├── requirements.txt                    # Librerías necesarias para ejecutar el proyecto
└── main.py                             # Script principal para correr todo el pipeline
´´´

## Ejecución del Proyecto

1. Clonar el repositorio
2. Crear un entorno virtual e instalar dependencias:

´´´
python -m venv .venv
source .venv/bin/activate   # En Linux/Mac
.venv\Scripts\activate       # En Windows
pip install -r requirements.txt
´´´

3. Cómo ejecutar el proyecto

Opción 1: Desde Jupyter Notebook ejecutando los notebooks en orden:
1_preprocessing.ipynb → 2_supervised_models.ipynb → 3_unsupervised_models.ipynb → 4_visualizations.ipynb

Opción 2: Desde terminal (modo script):

python main.py


El script principal correrá todo el pipeline: preprocesamiento, entrenamiento y evaluación.

## Metodología
#### Aprendizaje Supervisado

Se entrenarán los siguientes modelos:

Árboles de Decisión

K-Vecinos Más Cercanos (KNN)

Máquinas de Vectores de Soporte (SVM)

Redes Neuronales (MLP)

Cada modelo podrá evaluarse bajo varias configuraciones:

Diferente escalado de variables numéricas

Inclusión/exclusión de outliers

Con o sin balanceo de clases

Selección de diferentes subconjuntos de variables

Las métricas de evaluación incluirán: accuracy, precisión, recall, F1-score y, cuando aplique, curvas ROC y Precision-Recall.

#### Aprendizaje No Supervisado

Se aplicarán los modelos:

K-Means (utilizando el método del codo y Silhouette Score para determinar el número óptimo de clusters)

DBSCAN (determinando valores óptimos de ε y MinPts)

Se evaluarán los resultados mediante:

Inertia para K-Means

Silhouette Score para ambos

Visualización en 2D (a través de reducción dimensional — PCA o t-SNE) para interpretar los clusters hallados

Luego se interpretarán los segmentos resultantes de estilo de vida, identificando características comunes de cada cluster.

#### Visualización y Análisis

Generación de gráficos: histogramas, diagramas de caja (boxplots) para outliers, matrices de correlación, gráficos de barras para clases, curvas ROC/PR, gráficas de silhouette, etc.

Comparación de resultados: ¿Cuál modelo supervisado rinde mejor bajo qué configuración? ¿Qué segmentos surgen en el análisis no supervisado? ¿Cómo se relacionan con la variable objetivo?

Interpretación final y conclusiones: qué se puede aprender de los datos de estilo de vida, qué variables parecen clave, qué limitaciones hay, y sugerencias de mejora.