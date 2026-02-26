# Conociendo mis Datos (EDA)

---

## 1. Objetivo

Que el estudiante sea capaz de:

* Cargar un dataset real en Python.
* Identificar y clasificar los tipos de atributos.
* Obtener descripciones estadísticas básicas.
* Visualizar datos numéricos y categóricos.
* Calcular medidas de similitud y disimilitud entre instancias.
* Interpretar los resultados obtenidos.

---

## 2. Introducción Teórica

Antes de aplicar modelos de Machine Learning, es necesario comprender la estructura y características del conjunto de datos. Esta etapa se denomina **Análisis Exploratorio de Datos (EDA, Exploratory Data Analysis)**.

El EDA permite:

* Detectar valores faltantes.
* Identificar tipos de atributos.
* Analizar distribuciones.
* Evaluar dispersión y variabilidad.
* Detectar valores atípicos.
* Medir similitud entre instancias.

### 2.1 Tipos de Atributos

* **Nominal:** Categorías sin orden (Ej. ocupación, país).
* **Binario:** Dos categorías posibles (Ej. sexo, ingreso >50K).
* **Ordinal:** Categorías con orden definido (Ej. nivel educativo si se jerarquiza).
* **Numérico:** Valores cuantitativos.

  * Discreto: valores enteros contables.
  * Continuo: mediciones con posibles decimales.

### 2.2 Medidas Estadísticas

**Tendencia central**

* Media
* Mediana
* Moda

**Dispersión**

* Rango
* Cuartiles
* IQR (Rango intercuartílico)
* Varianza
* Desviación estándar

### 2.3 Medidas de Similitud y Disimilitud

* Distancia Manhattan (p = 1)
* Distancia Euclidiana (p = 2)
* Distancia de Minkowski (generalización)
* Hamming (para binarios)
* Jaccard (para binarios)
* Similitud coseno
* Distancia para tipos mixtos (aproximación tipo Gower)

---

## 3. Material Necesario

* Computadora con Python instalado.
* Jupyter Notebook.
* Librerías:

  * numpy
  * pandas
  * matplotlib

Datasets recomendados:
https://archive.ics.uci.edu/datasets

---

## 4. Desarrollo de la Práctica

* Los pasos para el desarrollo de la Práctica se describen a continuación. Y en el archivo [Practica_Conociendo_tus_datos](Practica_Conociendo_tus_datos.ipynb) se desglosa a manera de ejemplo parte del procedimiento. Se recomienda realizar los pasos y el análisis para el dataset que se incluye y posteriormente elegir un dataset que ustedes deseen analizar.

---

# Parte I — Carga y Limpieza de Datos

### Paso 1: Importar librerías

El estudiante deberá importar:

* numpy
* pandas
* matplotlib

### Paso 2: Cargar el dataset

Se deberá:

* Definir los nombres de columnas.
* Leer el archivo CSV.
* Mostrar las primeras 5 filas.

### Paso 3: Limpieza

* Reemplazar valores "?" por NaN.
* Contar valores faltantes por columna.
* Eliminar filas con valores faltantes.
* Mostrar dimensiones antes y después.

---

# Parte II — Identificación de Atributos

### Paso 4: Revisar tipos detectados por pandas

* Utilizar `df.dtypes`.
* Registrar los tipos en la bitácora.

### Paso 5: Clasificación Teórica

El estudiante deberá construir una tabla que contenga:

* Nombre del atributo.
* Tipo teórico (Nominal, Binario, Ordinal, Numérico).
* Tipo detectado por pandas.
* Número de valores únicos.

Se deberá justificar al menos 5 clasificaciones.

---

# Parte III — Estadística Descriptiva

### Paso 6: Estadística general

* Ejecutar `df.describe()`.

### Paso 7: Tendencia Central

Para las variables:

* Age
* Hours-per-week

Calcular:

* Media
* Mediana
* Moda

Registrar resultados.

### Paso 8: Dispersión

Para la variable:

* Hours-per-week

Calcular:

* Rango
* Q1
* Q3
* IQR
* Varianza
* Desviación estándar

Interpretar brevemente.

### Paso 9: Frecuencias en categóricas

Mostrar el Top-10 de:

* Occupation
* Native-country

---

# Parte IV — Visualización de Datos

### Paso 10: Histogramas

Generar histograma de:

* Age

### Paso 11: Densidad (KDE)

Graficar densidad de:

* Age

### Paso 12: Boxplot

Graficar boxplot de:

* Age
* Education-Num
* Hours-per-week

Identificar posibles valores atípicos.

### Paso 13: Scatter Plot

Graficar:

* Age vs Hours-per-week

Interpretar si existe alguna relación evidente.

### Paso 14: Gráfica de Barras

Graficar Top-10 de:

* Occupation

---

# Parte V — Medición de Similitud y Disimilitud

Se trabajará con una muestra aleatoria de 10 filas.

### Paso 15: Selección de muestra

* Utilizar `df.sample(10)`.

---

## 5.1 Distancias Numéricas

Seleccionar variables:

* Age
* Education-Num
* Hours-per-week

### Paso 16: Implementar función Minkowski

Calcular:

* Distancia Manhattan (p=1)
* Distancia Euclidiana (p=2)

Entre fila 0 y fila 1.

### Paso 17: Matriz de Distancias

Construir matriz 10x10 usando p=2.

Visualizar con `plt.imshow()`.

---

## 5.2 Distancias para Binarios

Convertir:

* Sex → 1 si Male, 0 si Female.
* Income → 1 si >50K, 0 si <=50K.

### Paso 18: Implementar Hamming

Calcular proporción de diferencias entre fila 0 y fila 1.

### Paso 19: Implementar Jaccard

Calcular similitud considerando coincidencias de 1.

---

## 5.3 Similitud Coseno

Estandarizar variables numéricas usando z-score.

### Paso 20: Implementar función de coseno

Construir matriz de similitud coseno.

Visualizar con mapa de calor.

---

## 5.4 Distancia para Tipos Mixtos

Implementar versión simplificada:

* Numéricas: normalizadas por rango.
* Categóricas: 0 si iguales, 1 si diferentes.
* Promedio final.

Construir matriz 10x10.

---


