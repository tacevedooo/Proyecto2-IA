# 📘 Proyecto: Clasificación y Agrupamiento de Aplicaciones de Google Play Store

#### Asignatura: Introducción a la Inteligencia Artificial

# 📌 Descripción General

Este proyecto implementa un sistema de análisis de datos y aprendizaje de máquinas sobre el dataset público “Google Play Store Apps” disponible en Kaggle.
El objetivo es aplicar y comparar diferentes técnicas de aprendizaje supervisado y no supervisado para tareas de clasificación y agrupamiento de aplicaciones 
según sus características (como categoría, calificación, tamaño, tipo, precios, etc.).

# 🎯 Objetivos
## 🎯 Objetivo General

Desarrollar una aplicación que, a partir de un dataset abierto, implemente y compare diferentes técnicas de aprendizaje de máquinas para la tarea de clasificación y agrupamiento.

## 🎯 Objetivos Específicos

Seleccionar y justificar un dataset con al menos 4 clases para la variable objetivo.

Aplicar preprocesamiento: normalización, manejo de outliers y balanceo de clases.

Implementar algoritmos supervisados: Árboles de Decisión, KNN, SVM y Redes Neuronales.

Implementar algoritmos no supervisados: K-Means y DBSCAN.

Evaluar los modelos mediante métricas de desempeño y curvas ROC/Precision-Recall.

Visualizar y analizar los resultados para comparar el comportamiento de los modelos bajo diferentes configuraciones.

# 📂 Estructura del Proyecto

```
📦 google-play-project
├── data/
│   ├── googleplaystore.csv        # Dataset original
│   ├── subset/                 # Subconjunto de datos a usar en el trabajo
|       ├── subset_googleplaystore_rows5200_seed5200 
│       ├── metadata.json   # Necesaria para luego reproducir exactamente el mismo subconjunto de datos
|   ├── processed/              # Datasets preprocesados (normalizados, balanceados, etc.)
│
├── notebooks/
│   ├── 1_preprocessing.ipynb       # Limpieza y preparación del dataset
│   ├── 2_supervised_models.ipynb   # Modelos supervisados (Árbol, KNN, SVM, NN)
│   ├── 3_unsupervised_models.ipynb # Modelos no supervisados (K-Means, DBSCAN)
│   ├── 4_visualizations.ipynb      # Gráficas y análisis de resultados
│
├── results/
│   ├── figures/                   # Gráficas generadas (barras, ROC, silhouette, etc.)
│   ├── tables/                    # Resultados en formato CSV
│
├── README.md                      # Descripción general del proyecto
├── requirements.txt               # Librerías necesarias para ejecutar el proyecto
└── main.py                        # Script principal para correr el proyecto
```

# ⚙️ Ejecución del Proyecto

## 🚀 1. Clonar el repositorio

## 🚀 2. Crear un entorno virtual e instalar dependencias:

   ```bash
   python -m venv .venv
   source .venv/bin/activate   # En Linux/Mac
   .venv\Scripts\activate    # En Windows
   pip install -r requirements.txt
   ```

## 🚀 3. Cómo ejecutar el proyecto
### Opción 1: Desde Jupyter Notebook

Ejecuta los notebooks en orden:

1_preprocessing.ipynb

2_supervised_models.ipynb

3_unsupervised_models.ipynb

4_visualizations.ipynb

### Opción 2: Desde terminal (modo script)
python main.py

El script main.py ejecutará todo el pipeline: preprocesamiento, entrenamiento y evaluación.

# 📊 Metodología
## 🧩 Aprendizaje Supervisado

### Se entrenaron los siguientes modelos:

Árboles de Decisión

K-Vecinos Más Cercanos (KNN)

Máquinas de Vectores de Soporte (SVM)

Redes Neuronales (MLP)

### Cada modelo se evaluó en 8 configuraciones diferentes según:

Conversión y escalado de características categóricas

Inclusión o exclusión de outliers

Balanceo o desbalanceo de clases

### Las métricas de evaluación fueron:

Accuracy

Precisión

Recall

F1-score

Además, se generaron curvas ROC y Precision-Recall para el caso 8.

## 🧭 Aprendizaje No Supervisado

### Se aplicaron los modelos:

K-Means (con método del codo y Silhouette Score)

DBSCAN (determinando valores óptimos de ε y MinPts)

### Se evaluaron los resultados con:

Inertia

Silhouette Score

Y se visualizaron los clusters en 2D para interpretar los patrones encontrados.
