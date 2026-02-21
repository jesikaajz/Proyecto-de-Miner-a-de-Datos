cat << 'EOF' > README.md
# 🌍 Clasificación de Severidad en Incidentes Migratorios

## 📌 Descripción del Proyecto

Este proyecto desarrolla un pipeline completo de Machine Learning para clasificar la severidad de incidentes migratorios a partir del **Global Missing Migrants Dataset**.

El objetivo es predecir el nivel de severidad de un incidente (`Baja`, `Media`, `Alta`) en función de características geográficas, temporales y contextuales.

Incluye:

- 📊 Data Understanding
- 🧹 Data Cleaning robusto
- 🎯 Creación de variable objetivo
- 🚫 Eliminación de data leakage
- ✂️ Train/Test Split estratificado
- 🧠 Entrenamiento y comparación de múltiples modelos
- 📈 Evaluación estadística avanzada

---

## 🗂 Dataset

El dataset contiene información histórica sobre incidentes migratorios con variables como:

- Número de fallecidos
- Número estimado de desaparecidos
- Región del incidente
- Año
- Causa de muerte
- Coordenadas geográficas

Variable objetivo original:

Total Number of Dead and Missing

---

## 🎯 Creación de Variable Objetivo

Se transforma el problema en clasificación multiclase:

| Total Dead & Missing | Severidad |
|----------------------|-----------|
| 0 – 2                | Baja      |
| 3 – 10               | Media     |
| > 10                 | Alta      |

---

## 🧹 Data Cleaning

Incluye:

- Eliminación de duplicados
- Conversión segura de numéricas
- Corrección de valores negativos
- Separación y validación de coordenadas
- Reconstrucción coherente de totales
- Eliminación de registros inconsistentes

---

## 🔐 Eliminación de Leakage

Se eliminan las variables directamente relacionadas con la variable objetivo:

- Total Number of Dead and Missing
- Number of Dead
- Minimum Estimated Number of Missing
- Number of Survivors
- Number of Females
- Number of Males
- Number of Children

---

## ✂️ Train/Test Split

- 80% Train
- 20% Test
- Estratificado por clase

---

## ⚙️ Preprocesamiento

- Imputación sin leakage (mediana/moda)
- Reducción de cardinalidad
- Tratamiento de outliers
- OneHot Encoding
- Escalado (modelos lineales)
- Feature Selection (SelectKBest)

---

## 🤖 Modelos Entrenados

- Naive Bayes
- KNN
- SVM (Linear, Poly, RBF)
- Decision Tree
- Random Forest
- Extra Trees
- AdaBoost
- Bagging

Optimización basada en F1-weighted.

---

## 📊 Resultados Finales

| Modelo          | Accuracy | F1-weighted |
|----------------|----------|------------|
| SVM            | 0.808    | 0.7848     |
| Random Forest  | 0.806    | 0.7900     |
| Extra Trees    | 0.792    | 0.7827     |
| AdaBoost       | 0.801    | 0.7632     |
| Decision Tree  | 0.767    | 0.7667     |
| KNN            | 0.727    | 0.7520     |
| Naive Bayes    | 0.583    | 0.6426     |

---

## 📈 Evaluación Estadística

- McNemar Test
- Intervalos de confianza 95%
- Bootstrap para F1
- Precision–Recall Curves
- Matrices de confusión

---

## 🛠 Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- Imbalanced-learn
- Seaborn
- Matplotlib
- Statsmodels

---

## ▶ Cómo Ejecutar

Instalar dependencias:

pip install -r requirements.txt

Ejecutar notebook:

PRACTICA_JESIKA_JIMENEZ_GERARD_CHAPARRO.ipynb

---

## 👩‍💻 Autores

- Jesika Jiménez  
- Gerard Chaparro  

---

## 🏁 Estado

Proyecto completo con validación estadística y comparación robusta de modelos.

EOF
