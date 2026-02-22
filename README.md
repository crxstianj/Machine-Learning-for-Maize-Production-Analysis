# Machine Learning for Maize Production Analysis

Sistema de análisis y predicción de la producción de maíz utilizando técnicas de **Machine Learning** aplicadas a datos agrícolas. El proyecto busca identificar variables clave que influyen en el rendimiento del cultivo y generar modelos predictivos que apoyen la toma de decisiones en el sector agrícola.

---

## Descripción del Proyecto

Guanajuato es un estado con alta producción de maíz; sin embargo, la variabilidad espacial y temporal en los rendimientos limita la eficiencia productiva. Este proyecto desarrolla un flujo analítico completo para integrar múltiples fuentes de datos agrícolas y construir modelos predictivos que permitan identificar los factores más influyentes en el rendimiento del cultivo.

El proyecto implementa un pipeline de ciencia de datos que permite:

- Analizar factores que afectan la producción de maíz.
- Integrar datos agrícolas, climáticos y de suelo.
- Incorporar índices de vegetación obtenidos por satélite.
- Entrenar modelos predictivos avanzados.
- Evaluar desempeño y sobreajuste.
- Identificar variables clave que impactan el rendimiento.
- Generar conocimiento útil para optimizar la producción agrícola.

---

## Fuente de Datos

Los datos base fueron proporcionados por la empresa **GPA**, incluyendo:

- Datos de siembra y cosecha georreferenciados.
- Datos de suelo.
- Datos climáticos.

---

## Data Engineering

El proyecto incluyó un proceso completo de ingeniería de datos para integrar, transformar y enriquecer múltiples fuentes de información agrícola y geoespacial antes del modelado.

El pipeline implementado consistió en:

### Integración de Datos Geoespaciales
- Conversión de datasets a estructuras geoespaciales.
- Reproyección de coordenadas a sistema métrico (UTM).
- Unión espacial por proximidad entre:
  - puntos de siembra
  - puntos de cosecha
  - muestras de suelo
- Generación de un dataset consolidado para el modelado.

### Enriquecimiento con Datos Satelitales
- Obtención de imágenes satelitales multiespectrales.
- Cálculo de índices de vegetación:
  - NDVI
  - GNDVI
  - NDRE
  - NDMI
  - SAVI
- Extracción de valores promedio por punto de muestreo.
- Incorporación de variables espectrales al dataset final.

### Limpieza y Transformación
- Detección y manejo de valores nulos.
- Eliminación de duplicados.
- Normalización de unidades.
- Validación de formatos temporales.
- Generación de variables derivadas.

### Generación del Dataset Final
- Integración de variables de siembra, suelo, clima y vegetación.
- Consolidación de múltiples fuentes en un único dataset.
- Preparación del dataset para análisis y modelado.

Este proceso permitió construir un dataset enriquecido que captura relaciones complejas entre variables agronómicas, ambientales y espectrales, facilitando el entrenamiento de modelos predictivos robustos.

---

## Objetivos

- Identificar variables clave en la producción de maíz.
- Aplicar técnicas de análisis de datos.
- Realizar selección de modelos.
- Reducir características mediante optimización multiobjetivo.
- Minimizar el sobreajuste.
- Analizar la influencia de variables relevantes en el rendimiento.

---

## Tecnologías Utilizadas

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- Pytorch
- Matplotlib
- Seaborn
- Algoritmos Genéticos 

---

## Metodología

El proyecto sigue un flujo reproducible de ciencia de datos:

1. Exploración de datos (EDA)
2. Limpieza e integración de datos
3. Ingeniería de características
4. Selección de modelos
5. Optimización multiobjetivo
6. Evaluación de sobreajuste
7. Interpretación de variables relevantes
8. Refinamiento del modelo final

Durante el análisis se identificaron relaciones no lineales entre las variables, por lo que se descartaron modelos lineales y se utilizaron modelos más flexibles.

---

## Selección de Modelo

Se realizó un proceso sistemático de selección de modelo evaluando distintos enfoques:

- Redes neuronales
- Modelos basados en árboles
- Modelos basados en distancias
- Modelos neurodifusos

Se utilizaron estrategias evolutivas para:

- Selección automática de características.
- Optimización de hiperparámetros.
- Reducción de características maximizando el R².
- Minimización del sobreajuste mediante optimización multiobjetivo.

Finalmente, el **modelo neurodifuso** fue seleccionado como modelo final por su mejor desempeño predictivo.

> Nota: Durante el proceso se evaluaron distintos modelos (ej. XGBoost, Random Forest), pero el modelo final del proyecto es el neurodifuso.

---

## Estructura del Proyecto

```
Machine-Learning-for-Maize-Production-Analysis/
│
├── Analisis.ipynb   # Análisis de datos de variables clave obtenidas de los modelos
├── Main2.ipynb      # Selección de modelo y optimización evolutiva
├── Main3.ipynb      # Refinamiento del modelo final y análisis de variables relevantes
```

### Descripción de Notebooks

### Analisis.ipynb
- Análisis exploratorio de las variables clave obtenidas de los modelos.
- Estudio de relaciones entre variables y rendimiento.
- Visualización de correlaciones.
- Interpretación de factores relevantes.

### Main2.ipynb — Selección de Modelo
- Prueba de múltiples modelos de Machine Learning.
- Optimización evolutiva simple.
- Optimización multiobjetivo para:
  - reducir características
  - aumentar R²
  - reducir sobreajuste
- Evaluación de desempeño y generalización.
- Selección del mejor modelo.

### Main3.ipynb — Refinamiento del Modelo
- Perfeccionamiento del modelo seleccionado.
- Evaluación del impacto de variables relevantes.
- Eliminación de variables irrelevantes.
- Análisis de cómo las variables clave influyen en la predicción.

---

## Resultados

- Identificación de factores determinantes en la producción de maíz.
- Captura de relaciones no lineales entre variables agrícolas.
- Reducción de dimensionalidad mediante optimización evolutiva.
- Modelo neurodifuso con mejor desempeño predictivo (MAE 1.540).
- Identificación de variables agronómicas y climáticas más influyentes.
- Presentación y comunicación de los principales resultados y hallazgos del análisis, incluyendo la interpretación de variables clave y el impacto de los factores estudiados.

---

## Aplicaciones

- Agricultura de precisión.
- Optimización de producción.
- Análisis predictivo.
- Soporte a decisiones.
- Manejo inteligente de recursos.

---

## Instalación

### Clonar repositorio

```bash
git clone https://github.com/crxstianj/Machine-Learning-for-Maize-Production-Analysis.git
cd Machine-Learning-for-Maize-Production-Analysis
```

### Instalar dependencias

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter torch
```

---

## Autor

**Cristian Jesús Silva Medel**  
