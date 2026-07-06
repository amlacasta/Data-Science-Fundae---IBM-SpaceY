# SpaceY — Predicción de Aterrizaje del Falcon 9

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightgrey)
![SQL](https://img.shields.io/badge/SQL-Exploratory%20Analysis-informational)
![Scikit--learn](https://img.shields.io/badge/Modeling-Scikit--learn-orange)
![Machine Learning](https://img.shields.io/badge/Use%20Case-Classification-green)
![Status](https://img.shields.io/badge/Status-IBM%20Capstone%20Project-success)

## 1. Resumen ejecutivo

Este proyecto corresponde al **capstone de IBM SkillsBuild / Data Science** sobre SpaceX, adaptado como evidencia de portfolio para mostrar un flujo completo de ciencia de datos:

```text
obtención de datos → limpieza → análisis exploratorio → SQL → preparación de features → modelos de clasificación → comparación de resultados
```

El objetivo del proyecto es predecir si la **primera etapa del cohete Falcon 9** aterrizará correctamente después del lanzamiento.

La reutilización de la primera etapa es clave porque reduce de forma importante el coste de cada misión. Por tanto, anticipar la probabilidad de aterrizaje permite estimar mejor el riesgo operativo y económico asociado a un lanzamiento.

El proyecto combina varias competencias esenciales de un perfil Data Science junior / analista avanzado:

- consumo de APIs,
- web scraping,
- limpieza y transformación de datos,
- análisis exploratorio,
- consultas SQL,
- preparación de variables para machine learning,
- entrenamiento y comparación de modelos de clasificación,
- interpretación de resultados.

---

## 2. Contexto del problema

SpaceX revolucionó el sector aeroespacial al reutilizar partes críticas de sus cohetes, especialmente la primera etapa del Falcon 9.

Desde una perspectiva de negocio, el problema puede formularse así:

```text
Si se puede predecir si la primera etapa aterrizará con éxito,
se puede estimar mejor el coste, el riesgo y la competitividad de un lanzamiento.
```

El caso tiene una lectura muy interesante para portfolio porque transforma datos técnicos de lanzamientos espaciales en una pregunta de negocio clara:

> ¿Qué variables ayudan a explicar el éxito o fracaso del aterrizaje de la primera etapa?

---

## 3. Objetivo del proyecto

Construir un flujo de análisis y modelado capaz de:

- recopilar datos históricos de lanzamientos de SpaceX,
- enriquecerlos desde distintas fuentes,
- limpiar y preparar el dataset,
- crear una variable objetivo binaria,
- explorar patrones relevantes,
- consultar información mediante SQL,
- entrenar varios modelos de clasificación,
- comparar su rendimiento sobre datos de test.

La variable objetivo del proyecto es:

```text
Class = 1 → aterrizaje exitoso
Class = 0 → aterrizaje no exitoso
```

---

## 4. Preguntas analíticas

El proyecto busca responder a preguntas como:

- ¿Qué porcentaje de lanzamientos terminó con aterrizaje exitoso?
- ¿Cómo evoluciona el éxito de aterrizaje a lo largo del tiempo?
- ¿Qué sitios de lanzamiento presentan mejores resultados?
- ¿Qué órbitas concentran más misiones exitosas?
- ¿Existe relación entre masa de carga útil y probabilidad de éxito?
- ¿Qué modelo de clasificación predice mejor el aterrizaje?
- ¿Qué limitaciones tiene el resultado cuando el dataset es pequeño?

---

## 5. Dataset

El proyecto trabaja con datos históricos de lanzamientos de SpaceX Falcon 9.

### 5.1 Fuentes de datos

| Fuente | Uso principal |
|---|---|
| SpaceX API | Recopilación inicial de datos de lanzamientos, cohetes, cargas útiles, órbitas y localizaciones |
| Wikipedia | Extracción complementaria de registros históricos mediante web scraping |
| Dataset IBM / Skills Network | Dataset preparado para ejercicios de SQL, EDA y machine learning |

### 5.2 Unidad de análisis

```text
1 fila = 1 lanzamiento / misión Falcon 9
```

### 5.3 Variables principales

| Categoría | Variables |
|---|---|
| Identificación | `FlightNumber`, `Date`, `BoosterVersion`, `Serial` |
| Misión | `PayloadMass`, `Orbit`, `LaunchSite` |
| Resultado | `Outcome`, `Class` |
| Reutilización | `Flights`, `GridFins`, `Reused`, `Legs`, `LandingPad`, `ReusedCount` |
| Localización | `Latitude`, `Longitude` |
| Ingeniería / configuración | `Block`, `BoosterVersion` |

---

## 6. Estructura del repositorio

```text
Data-Science-Fundae---IBM-SpaceY/
│
├── 1 jupyter-labs-spacex-data-collection-api v2.ipynb
├── 2 jupyter-labs-webscraping  completo.ipynb
├── labs_jupyter_spacex_Data_wrangling_v2 completo.ipynb
├── 3 jupyter-labs-eda-sql-coursera_sqllite (completo).ipynb
├── 6 SpaceX_Machine Learning Prediction_Part_5 completo.ipynb
│
└── README.md
```

El repositorio contiene actualmente cinco notebooks principales. La numeración procede del itinerario original del capstone de IBM, por eso algunos nombres no siguen todavía una nomenclatura homogénea.

---

## 7. Metodología

El proyecto sigue una secuencia progresiva de trabajo.

| Notebook | Objetivo | Output principal |
|---|---|---|
| [`1 jupyter-labs-spacex-data-collection-api v2.ipynb`](./1%20jupyter-labs-spacex-data-collection-api%20v2.ipynb) | Recopilar datos desde la SpaceX API y realizar una primera limpieza | Dataset inicial de lanzamientos |
| [`2 jupyter-labs-webscraping  completo.ipynb`](./2%20jupyter-labs-webscraping%20%20completo.ipynb) | Extraer datos históricos desde Wikipedia con BeautifulSoup | Tabla estructurada de lanzamientos |
| [`labs_jupyter_spacex_Data_wrangling_v2 completo.ipynb`](./labs_jupyter_spacex_Data_wrangling_v2%20completo.ipynb) | Limpiar variables, tratar valores faltantes y crear la variable `Class` | Dataset preparado para análisis |
| [`3 jupyter-labs-eda-sql-coursera_sqllite (completo).ipynb`](./3%20jupyter-labs-eda-sql-coursera_sqllite%20(completo).ipynb) | Realizar análisis exploratorio mediante SQL sobre SQLite | Respuestas analíticas mediante consultas |
| [`6 SpaceX_Machine Learning Prediction_Part_5 completo.ipynb`](./6%20SpaceX_Machine%20Learning%20Prediction_Part_5%20completo.ipynb) | Entrenar y comparar modelos de clasificación | Comparativa de modelos ML |

---

## 8. Análisis exploratorio

El análisis exploratorio permite entender qué factores pueden estar relacionados con el éxito del aterrizaje.

Áreas analizadas:

- distribución de lanzamientos por sitio,
- evolución temporal de los lanzamientos,
- relación entre masa de carga útil y resultado,
- comportamiento por tipo de órbita,
- frecuencia de éxitos y fracasos,
- patrones asociados a reutilización del booster.

La parte SQL refuerza una competencia clave: traducir preguntas de negocio a consultas estructuradas.

Ejemplos de análisis abordados:

- número total de lanzamientos,
- masas de carga útil por misión,
- lanzamientos por sitio,
- resultados por órbita,
- misiones exitosas frente a no exitosas.

---

## 9. Preparación del dato

La fase de data wrangling es una de las partes más importantes del proyecto.

Incluye:

- revisión de valores nulos,
- tratamiento de columnas categóricas,
- codificación del resultado del aterrizaje,
- creación de la variable binaria `Class`,
- preparación del dataset para entrenamiento supervisado.

La lógica principal de clasificación es:

```text
aterrizaje exitoso     → 1
aterrizaje no exitoso  → 0
```

Este paso convierte un dataset histórico en un problema de **machine learning supervisado**.

---

## 10. Modelos de machine learning

En el notebook final se entrenan y comparan varios modelos clásicos de clasificación.

| Modelo | Técnica |
|---|---|
| Logistic Regression | Clasificación lineal interpretable |
| Support Vector Machine | Clasificación con distintos kernels |
| Decision Tree | Modelo basado en reglas de decisión |
| K-Nearest Neighbors | Clasificación por proximidad |

El flujo de modelado incluye:

1. selección de variables predictoras,
2. estandarización de datos,
3. partición train/test,
4. búsqueda de hiperparámetros con `GridSearchCV`,
5. evaluación sobre test,
6. comparación final de modelos.

---

## 11. Evaluación

La evaluación se realiza con un conjunto de test del 20%.

El propio notebook indica que el conjunto de test contiene solo **18 observaciones**, por lo que los resultados deben interpretarse con prudencia.

### 11.1 Resultados obtenidos

| Modelo | Accuracy test |
|---|---:|
| Logistic Regression | 0.8333 |
| SVM | 0.8333 |
| KNN | 0.8333 |
| Decision Tree | 0.7222 |

### 11.2 Interpretación

Los mejores resultados empatan en test:

```text
Logistic Regression = SVM = KNN = 0.8333
```

Decision Tree queda por debajo con una accuracy de `0.7222`.

Desde una perspectiva de portfolio, este resultado es útil porque permite explicar algo importante: no siempre gana el modelo más complejo. En datasets pequeños, modelos sencillos e interpretables pueden competir muy bien.

---

## 12. Impacto de negocio

Aunque se trata de un proyecto académico, el caso tiene una lectura empresarial clara.

Una predicción fiable del aterrizaje permite:

### Coste

- estimar mejor el coste esperado de una misión,
- valorar el impacto de reutilizar o no reutilizar la primera etapa,
- comparar competitividad frente a otros proveedores.

### Riesgo operativo

- identificar configuraciones de misión con mayor probabilidad de fallo,
- analizar patrones por sitio de lanzamiento, órbita o carga útil,
- anticipar escenarios de mayor incertidumbre.

### Decisión comercial

- apoyar estimaciones para licitaciones,
- construir escenarios de coste,
- mejorar la planificación de ofertas frente a competidores.

---

## 13. Cómo reproducir el proyecto

### 13.1 Requisitos

El proyecto está desarrollado en notebooks de Python.

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
```

Instalación orientativa:

```bash
pip install pandas numpy requests beautifulsoup4 matplotlib seaborn sqlalchemy ipython-sql scikit-learn
```

### 13.2 Orden de ejecución recomendado

```text
1 jupyter-labs-spacex-data-collection-api v2.ipynb
2 jupyter-labs-webscraping  completo.ipynb
labs_jupyter_spacex_Data_wrangling_v2 completo.ipynb
3 jupyter-labs-eda-sql-coursera_sqllite (completo).ipynb
6 SpaceX_Machine Learning Prediction_Part_5 completo.ipynb
```

### 13.3 Entorno recomendado

- Jupyter Notebook
- Google Colab
- IBM Skills Network Labs

Algunos notebooks dependen de datasets remotos del curso, por lo que es recomendable ejecutarlos con conexión a internet.

---

## 14. Fortalezas del proyecto

Este repositorio demuestra una base técnica sólida en varias fases del ciclo de vida de un proyecto Data Science.

| Área | Evidencia |
|---|---|
| Data acquisition | Consumo de API y extracción web |
| Data wrangling | Limpieza, transformación y creación de variable objetivo |
| SQL | Consultas analíticas sobre dataset estructurado |
| EDA | Exploración de variables relevantes del problema |
| Machine Learning | Comparación de varios modelos supervisados |
| Comunicación | Documentación del flujo completo en README |

---

## 15. Limitaciones

Limitaciones principales del estado actual del proyecto:

- es un proyecto académico guiado por IBM,
- los notebooks conservan parte del formato original del curso,
- el dataset de test es pequeño,
- no hay todavía dashboard interactivo publicado,
- no se incluye una app de explotación del modelo,
- no hay pipeline automatizado de entrenamiento,
- no se han añadido conclusiones ejecutivas dentro de todos los notebooks,
- los nombres de archivos podrían homogeneizarse para una presentación más profesional.

---

## 16. Próximos pasos recomendados

Para convertir este proyecto en una pieza más potente de portfolio, se recomienda:

1. Renombrar notebooks con una estructura limpia:

```text
01_data_collection_api.ipynb
02_web_scraping.ipynb
03_data_wrangling.ipynb
04_eda_sql.ipynb
05_machine_learning_prediction.ipynb
```

2. Añadir una carpeta `data/` con explicación de fuentes.
3. Crear una carpeta `reports/figures/` con gráficos exportados.
4. Incorporar un notebook adicional de conclusiones ejecutivas.
5. Añadir una matriz de confusión final por modelo.
6. Crear una pequeña app o dashboard con Streamlit o Plotly.
7. Guardar el modelo final con `joblib`.
8. Añadir un `requirements.txt`.
9. Incluir una sección final de storytelling orientada a negocio.

---

## 17. Conclusión

Este proyecto es una buena evidencia de fundamentos técnicos de Data Science.

Su valor principal no está en el dominio aeroespacial en sí, sino en demostrar que se domina el flujo completo:

```text
buscar datos → limpiarlos → analizarlos → consultarlos → modelarlos → evaluar resultados → comunicar conclusiones
```

Dentro de un portfolio profesional, funciona especialmente bien como proyecto de base para acreditar competencias generales antes de presentar proyectos más personalizados y aplicados a negocio, como forecasting, operaciones, pricing o analítica avanzada.

El siguiente salto natural sería evolucionarlo desde un capstone académico hacia una versión más ejecutiva, con naming limpio, visualizaciones finales, conclusiones de negocio y una pequeña interfaz de explotación del modelo.
