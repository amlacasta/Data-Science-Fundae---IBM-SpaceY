# SpaceY — Proyecto de estudio IBM Data Science

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightgrey)
![SQL](https://img.shields.io/badge/SQL-EDA-informational)
![Scikit--learn](https://img.shields.io/badge/ML-Scikit--learn-orange)
![Course](https://img.shields.io/badge/Type-IBM%20Learning%20Project-success)

## 1. Qué es este repositorio

Este repositorio recoge un **proyecto de estudio realizado durante la formación de IBM / Skills Network en Data Science**.

No está planteado como un proyecto profesional para mostrar a empresas ni como un caso de negocio propio. Su función principal es conservar de forma ordenada el trabajo realizado durante el curso y dejar trazabilidad del aprendizaje técnico.

El caso de estudio trabaja con datos de lanzamientos de **SpaceX Falcon 9** y plantea una pregunta de clasificación:

```text
¿Aterrizará correctamente la primera etapa del cohete Falcon 9?
```

El valor del repositorio está en practicar el flujo completo de un proyecto de ciencia de datos:

```text
API → web scraping → limpieza → análisis exploratorio → SQL → machine learning → resumen ejecutivo
```

---

## 2. Objetivos de aprendizaje

El objetivo no era crear un producto final, sino practicar competencias fundamentales:

- obtener datos desde una API,
- extraer información mediante web scraping,
- limpiar y preparar datos,
- construir una variable objetivo,
- realizar análisis exploratorio,
- consultar datos con SQL,
- entrenar modelos clásicos de clasificación,
- comparar resultados de modelos,
- documentar el trabajo realizado.

---

## 3. Contexto del caso SpaceX

SpaceX reutiliza la primera etapa del Falcon 9 para reducir el coste de los lanzamientos. En el curso se plantea que, si se puede estimar si esa primera etapa aterrizará correctamente, se puede aproximar mejor el riesgo y el coste asociado a una misión.

La variable objetivo utilizada es:

```text
Class = 1 → aterrizaje exitoso
Class = 0 → aterrizaje no exitoso
```

---

## 4. Estructura del repositorio

```text
Data-Science-Fundae---IBM-SpaceY/
│
├── notebooks/
│   ├── 01_data_collection_api.ipynb
│   ├── 02_web_scraping.ipynb
│   ├── 03_data_wrangling.ipynb
│   ├── 04_eda_sql.ipynb
│   ├── 05_machine_learning_prediction.ipynb
│   └── 06_executive_summary.ipynb
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── README.md
│
├── reports/
│   ├── figures/
│   └── README.md
│
├── dashboard/
│   └── spacey_learning_dashboard.html
│
├── requirements.txt
└── README.md
```

---

## 5. Notebooks

| Notebook | Descripción | Finalidad de aprendizaje |
|---|---|---|
| `01_data_collection_api.ipynb` | Obtención de datos desde la SpaceX API | Practicar consumo de APIs y transformación inicial |
| `02_web_scraping.ipynb` | Extracción de tablas históricas desde Wikipedia | Practicar web scraping con BeautifulSoup |
| `03_data_wrangling.ipynb` | Limpieza, tratamiento de variables y creación de `Class` | Preparar datos para análisis y ML |
| `04_eda_sql.ipynb` | Análisis exploratorio mediante SQL / SQLite | Traducir preguntas analíticas a consultas SQL |
| `05_machine_learning_prediction.ipynb` | Entrenamiento y comparación de modelos ML | Practicar clasificación supervisada |
| `06_executive_summary.ipynb` | Resumen final del aprendizaje y resultados | Sintetizar el proyecto de forma clara |

---

## 6. Datos utilizados

El proyecto trabaja con datos procedentes de:

| Fuente | Uso |
|---|---|
| SpaceX API | Datos iniciales de lanzamientos |
| Wikipedia | Registros históricos complementarios |
| IBM Skills Network | Datasets formativos para SQL y machine learning |

No se incluyen datos confidenciales ni datos propios. Algunos notebooks descargan los datos directamente desde fuentes remotas del curso.

---

## 7. Flujo de trabajo

El flujo recomendado de ejecución es:

```text
1. notebooks/01_data_collection_api.ipynb
2. notebooks/02_web_scraping.ipynb
3. notebooks/03_data_wrangling.ipynb
4. notebooks/04_eda_sql.ipynb
5. notebooks/05_machine_learning_prediction.ipynb
6. notebooks/06_executive_summary.ipynb
```

---

## 8. Modelos evaluados

En el notebook de machine learning se comparan varios modelos clásicos de clasificación:

| Modelo | Resultado test accuracy |
|---|---:|
| Logistic Regression | 0.8333 |
| SVM | 0.8333 |
| KNN | 0.8333 |
| Decision Tree | 0.7222 |

Los mejores modelos empatan en accuracy. El resultado debe interpretarse con prudencia porque el conjunto de test es pequeño.

---

## 9. Mini dashboard

Se incluye un dashboard HTML sencillo en:

```text
dashboard/spacey_learning_dashboard.html
```

Su finalidad no es productiva, sino didáctica: resume el flujo del curso, los notebooks, los modelos utilizados y las principales conclusiones de aprendizaje.

---

## 10. Instalación

Crear un entorno virtual e instalar dependencias:

```bash
pip install -r requirements.txt
```

Dependencias principales:

```text
pandas
numpy
requests
beautifulsoup4
matplotlib
seaborn
sqlalchemy
ipython-sql
scikit-learn
jupyter
```

---

## 11. Limitaciones

Este repositorio debe leerse como material de aprendizaje.

Limitaciones principales:

- procede de un curso guiado de IBM,
- los notebooks conservan parte del formato original del laboratorio,
- algunos datos se descargan desde recursos externos del curso,
- el conjunto de test del modelo final es pequeño,
- no hay validación temporal avanzada,
- no se trata de una solución productiva,
- no representa un caso profesional propio.

---

## 12. Qué demuestra este curso

Aunque no sea un proyecto profesional, sí deja constancia de competencias técnicas importantes:

| Competencia | Evidencia en el repositorio |
|---|---|
| Python | Uso de notebooks y librerías de análisis |
| APIs | Extracción de datos desde SpaceX API |
| Web scraping | Extracción de tablas desde Wikipedia |
| Pandas / NumPy | Limpieza y transformación de datos |
| SQL | Consultas analíticas sobre el dataset |
| Visualización | Gráficos exploratorios con Matplotlib / Seaborn |
| Machine Learning | Modelos supervisados con Scikit-learn |
| Documentación | README, dashboard didáctico y notebook resumen |

---

## 13. Conclusión

Este repositorio queda organizado como **archivo de aprendizaje técnico** del curso IBM Data Science.

No pretende competir con proyectos propios más avanzados, pero sí cumple una función importante: conservar de forma clara el recorrido de aprendizaje y mostrar la progresión desde fundamentos básicos hasta un flujo completo de clasificación supervisada.

El siguiente paso natural, fuera de este repositorio, es aplicar estos conocimientos en proyectos propios con más contexto de negocio, datos diseñados a medida y una narrativa analítica más profesional.
