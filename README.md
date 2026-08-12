# Proyectos de Machine Learning

Colección de notebooks de Python que aplican distintas técnicas de aprendizaje automático (regresión, clasificación, clustering y reducción de dimensionalidad) sobre cuatro datasets: estadísticas de béisbol (MLB), diagnóstico de cáncer de mama, precio de acciones de Samsung y decisión de comprar vs. alquilar vivienda.

## Estructura del repositorio

```
.
├── data/          # Datasets originales en CSV
├── notebooks/     # Notebooks de análisis (Jupyter)
├── models/        # Modelos entrenados, serializados con joblib
├── figures/       # Gráficos generados por los notebooks
├── results/       # Resultados tabulares (p. ej. búsqueda de k en K-Means)
└── README.md
```

## Notebooks

| Notebook | Dataset | Técnica |
|---|---|---|
| [`SA_1_regresion_beisbol.ipynb`](notebooks/SA_1_regresion_beisbol.ipynb) | `beisbol.csv` | Regresión lineal y Ridge (con features polinómicas) |
| [`SA_2_clasificacion_breast_cancer.ipynb`](notebooks/SA_2_clasificacion_breast_cancer.ipynb) | `breast_cancer.csv` | Árbol de decisión (clasificación) |
| [`SA_3_clustering_samsung.ipynb`](notebooks/SA_3_clustering_samsung.ipynb) | `samsung.csv` | Clustering K-Means sobre series de tiempo financieras |
| [`SA_4_PCA_comprar_alquilar.ipynb`](notebooks/SA_4_PCA_comprar_alquilar.ipynb) | `comprar_alquilar.csv` | Análisis de componentes principales (PCA) |
| [`DE_1_clasificacion_breast_cancer.ipynb`](notebooks/DE_1_clasificacion_breast_cancer.ipynb) | `breast_cancer.csv` | Regresión logística (clasificación) |
| [`DE_2_regresion_beisbol.ipynb`](notebooks/DE_2_regresion_beisbol.ipynb) | `beisbol.csv` | Random Forest (regresión) |

Cada notebook sigue un flujo similar:

1. Carga y exploración del dataset (`data/`).
2. Visualización exploratoria (guardada en `figures/`).
3. División train/test y validación cruzada (K-Fold).
4. Ajuste de hiperparámetros con `GridSearchCV`.
5. Evaluación del modelo final con métricas relevantes (R², MAE, RMSE, accuracy, F1, ROC-AUC, silueta, etc.).
6. Persistencia del modelo entrenado en `models/` con `joblib`.

## Datasets

- **`beisbol.csv`**: turnos al bate (`bateos`) y carreras anotadas (`runs`) por equipo de la MLB.
- **`breast_cancer.csv`**: características de núcleos celulares para diagnóstico de tumores (benigno/maligno).
- **`samsung.csv`**: precio de cierre (`Close`) y volumen (`Volume`) histórico de la acción de Samsung.
- **`comprar_alquilar.csv`**: variables socioeconómicas (ingresos, gastos, hijos, etc.) y la decisión de comprar o alquilar vivienda.

## Requisitos

```bash
pip install joblib scikit-learn pandas matplotlib numpy jupyter
```

## Uso

1. Clona el repositorio.
2. Instala las dependencias (ver arriba).
3. Abre los notebooks desde la carpeta `notebooks/` con Jupyter:

   ```bash
   jupyter notebook notebooks/
   ```

4. Ejecuta las celdas en orden. Cada notebook lee sus datos desde `../data/` y guarda figuras/modelos en `../figures/` y `../models/` respectivamente.
