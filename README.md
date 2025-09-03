# Primer Parcial - IA para la Economía 2025-2
**Universidad de los Andes - Facultad de Economía**

## 📋 Información del Proyecto

Este repositorio contiene el desarrollo del primer parcial de la materia "IA para la Economía", enfocado en la aplicación de algoritmos de Machine Learning clásico para resolver problemas económicos utilizando el dataset de consumo de alcohol estudiantil.

### 🎯 Objetivos
- Aplicar algoritmos de aprendizaje supervisado y no supervisado
- Implementar modelos predictivos para análisis económico
- Desarrollar habilidades en procesamiento y análisis de datos
- Crear un pipeline completo desde la carga de datos hasta la evaluación de modelos

## 📊 Dataset

**Fuente**: scikit-learn/student-alcohol-consumption  
**Dimensiones**: 1,044 registros × 33 características  
**Variable objetivo**: G3 (calificación final del estudiante)

### Variables principales:
- **Demográficas**: school, sex, age, address, famsize
- **Educativas**: Medu, Fedu, studytime, failures, schoolsup
- **Sociales**: activities, romantic, goout, Dalc, Walc
- **Académicas**: G1, G2, G3 (calificaciones de períodos)

## 🛠️ Tecnologías Utilizadas

```python
# Librerías principales
pandas                 # Manipulación de datos
numpy                  # Operaciones numéricas
scikit-learn          # Algoritmos de ML
matplotlib & seaborn   # Visualización
xgboost               # Algoritmos de ensamble
```

## 🔬 Metodología

### 1. Exploración y Preprocesamiento
- **Carga del dataset** desde Hugging Face datasets
- **Análisis exploratorio** de distribuciones y correlaciones
- **Limpieza de datos** eliminando duplicados basado en características clave
- **Normalización** de variables numéricas usando StandardScaler
- **Codificación** de variables categóricas con LabelEncoder

### 2. Algoritmos Implementados

#### Aprendizaje Supervisado
- **Regresión Logística**: Modelo lineal con regularización
- **K-Nearest Neighbors (KNN)**: Clasificación basada en distancia
- **Support Vector Machine (SVM)**: Clasificación con kernels
- **Árboles de Decisión**: Modelos interpretables
- **Random Forest**: Ensamble de árboles
- **XGBoost**: Gradient boosting optimizado

#### Aprendizaje No Supervisado
- **K-Means Clustering**: Segmentación de estudiantes
- **PCA**: Reducción de dimensionalidad
- **Análisis de Silhouette**: Evaluación de clusters

### 3. Evaluación de Modelos
- **Validación cruzada** con StratifiedKFold
- **Métricas de clasificación**: accuracy, precision, recall, F1-score
- **Matrices de confusión** y curvas ROC
- **Comparación de rendimiento** entre algoritmos

## 📁 Estructura del Repositorio

```
├── notebooks/
│   └── Copia_de_Parcial1AI.ipynb    # Notebook principal
├── data/                             # Datos procesados
├── models/                           # Modelos entrenados
├── results/                          # Resultados y visualizaciones
├── docs/                            # Documentación adicional
└── README.md                        # Este archivo
```

## 🚀 Instrucciones de Uso

### Prerrequisitos
```bash
pip install pandas numpy scikit-learn matplotlib seaborn xgboost datasets
```

### Ejecución
1. Clonar el repositorio
2. Abrir el notebook en Google Colab o Jupyter
3. Ejecutar las celdas secuencialmente
4. Los resultados se guardarán automáticamente

## 📈 Resultados Principales

### Preprocesamiento
- **Datos originales**: 1,044 registros
- **Después de limpieza**: 662 registros únicos
- **Duplicados eliminados**: 382 registros

### Variables Procesadas
- **Numéricas estandarizadas**: 15 variables (age, Medu, Fedu, etc.)
- **Categóricas codificadas**: 13 variables (school, sex, address, etc.)

### Modelos Entrenados
- Implementación exitosa de 6 algoritmos supervisados
- Clustering con K-Means para segmentación
- Reducción dimensional con PCA
- Evaluación comparativa de rendimiento

## Curva ROC
Se evidencia que todos los modelos tienen un buen rendimiento, sin embargo, KNN con tiene el peor rendimiento de los tres modelos, ya que, detecta bien a los estudiantes que aprueban/reprueban, pero comete más falsos positivos. En cambio,  sobresale Randomforest, siendo este modelo el de mejor rendimiento de los tres, lo que implica que distingue con mucha precisión entre aprobar y reprobar.

## Modelos
Los tres modelos muestran buenos resultados : las accuracies son superiores a 0.84. 
- KNN: El recall es muy alto lo que significa que el modelo detecta casi todos los casos positivos pero tiene menor precisión y AUC, lo que indica que genera más FP 
- XGBoost: El modelo es confiable y robusto porque su AUC es muy alto lo que demuestra una excelente capacidad de distinguir entre clases. El recall y la precisión presentan un buen equilibrio. 
- RandomForest: El modelo minimiza los FP y discrimina con mayor eficiencia entre las clases. Tiene la mejor precisión y el mejor AUC 

## Validacion Cruzada
Random Forest alcanza los valores de F1 más altos en la validación cruzada y muestra una gran consistencia entre los distintos folds. KNN, en cambio, presenta el peor desempeño: sus F1-scores son claramente más bajos y con mayor variabilidad, lo que indica que depende más de la partición de datos que le toque. Por su parte, XGBoost también exhibe un rendimiento muy competitivo, con resultados cercanos a los de Random Forest, aunque con una ligera mayor dispersión en los folds.


## 💡 Aplicaciones Económicas

Este proyecto demuestra cómo los algoritmos de ML pueden aplicarse a:
- **Predicción de rendimiento académico** como proxy de capital humano
- **Segmentación de poblaciones** para políticas educativas focalizadas
- **Identificación de factores** socioeconómicos relevantes en educación
- **Optimización de recursos** educativos basada en perfiles estudiantiles

## 👥 Contribuidores

- **Equipo de desarrollo**: Adrian Montenegro Zamora, Daniel Esteban Gonzalez Vergara, Godwin Zuluaga Garcia, Jade Manon Nicolas, Juan Pablo Camacho Peña, Luis Alejandro Suarez Arevalo, Maria Alejandra Velasquez Chauta.
- **Profesor**: Camilo Vega Barbosa
- **Profesor complementario**: Daniel Aguirre

## 📚 Referencias

- Cortez, P. & Silva, A. (2008). Using Data Mining to Predict Secondary School Student Performance
- Scikit-learn documentation
- XGBoost documentation
- Curso "IA para la Economía" - Universidad de los Andes

## 📄 Licencia

Este proyecto se desarrolla con fines académicos para la Universidad de los Andes.

---

**Fecha de entrega**: Semana 5 - Segundo semestre 2025  
**Evaluación**: 50% presentación + 50% entregable en GitHub
