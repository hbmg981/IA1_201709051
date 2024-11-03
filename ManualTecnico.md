## LABORATORIO DE INTELIGENCIA ARTIFICIAL 1 - PROYECTO 2
### 201709051 - Heidy Beatríz Miranda Gámez
# Modelos de Machine Learning

# Manual Técnico

Este manual técnico describe varios modelos de Machine Learning implementados utilizando Tytus.js. Cada modelo se presenta con su respectiva teoría, método de aplicación y una tabla de parámetros y datos de entrada.

## Índice
1. [Regresión Lineal](#1-regresión-lineal)
2. [Regresión Polinomial](#2-regresión-polinomial)
3. [Árbol de Decisión](#3-árbol-de-decisión)
4. [Redes Neuronales](#4-redes-neuronales)
5. [Naive Bayes](#5-naive-bayes)
6. [K-Means](#6-k-means)
7. [K-Nearest Neighbor](#7-k-nearest-neighbor)

---

## 1. Regresión Lineal

## Descripción
La regresión lineal es un modelo estadístico que busca predecir un valor continuo a partir de una o más variables independientes. Este modelo se basa en la relación lineal entre las variables.

## Implementación del Modelo
El modelo permite cargar datos en formatos CSV o JSON, entrenar el modelo de regresión lineal y hacer predicciones sobre nuevos datos. Los resultados se visualizan en gráficos y tablas.

## Parámetros Utilizados
| Parámetro                | Descripción                                        | Tipo       |
|--------------------------|----------------------------------------------------|------------|
| `learning_rate`          | Tasa de aprendizaje que controla el ajuste del modelo | `float`    |
| `num_iterations`         | Número de iteraciones para el entrenamiento        | `int`      |
| `trainPercentage`        | Porcentaje de datos utilizados para el entrenamiento | `int` (0-100) |
| `newXValue`             | Valor de entrada para la predicción                | `float`    |

## Funciones Implementadas
### Función para procesar el contenido de un archivo CSV y extraer los valores de X e Y.
```javascript
function parseCSV(fileContent) {}
```
### Función para procesar el contenido de un archivo JSON y extraer los valores de X e Y.
```javascript
function parseJSON(fileContent) {}
```
### Event Listener para el input de archivos.
```javascript
document.getElementById('fileInput').addEventListener('change', function (event) { ... })
```
### Controlador de clic para el botón de entrenamiento.
```javascript
document.getElementById('trainButton').onclick = function () {}
```
### Controlador de clic para el botón de predicción.
```javascript
document.getElementById('predictButton').onclick = function () {}
```
### Controlador de clic para el botón de mostrar gráfico.
```javascript
document.getElementById('showGraphButton').onclick = function () {}
```
### Función que actualiza la tabla de resultados con los valores de X, Y y las predicciones de Y.
```javascript
function updateResultsTable(x, y, yPred) {}
```
### Función que actualiza la tabla de predicción con los valores de X, las predicciones de Y y el error porcentual.
```javascript
function updateDisplayTable(x, y, yPred) {}
```
### Función que dibuja el gráfico de regresión lineal utilizando Google Charts.
```javascript
function drawChart(data) {}
```
### Función que une los arrays en una estructura adecuada para ser utilizada por Google Charts.
```javascript
 function joinArrays(labelX, arrX, labelYTrain, arrYTrain, labelYPred, arrYPred) {}
```

## Ejemplo de Datos de Entrada (JSON)
Un ejemplo de archivo JSON que puede ser utilizado para cargar los datos:
```json
[
    { "x": 1, "y": 1 },
    { "x": 2, "y": 4 },
    { "x": 3, "y": 1 },
    { "x": 4, "y": 5 },
    { "x": 5, "y": 3 }
]
```

## Resultados
Los resultados incluyen:
- La tabla con los valores de entrada `X`, los valores reales `Y` y las predicciones `Y`.
- Gráfico que representa la línea de regresión y los datos.

---

## 2. Regresión Polinomial

## Descripción
La regresión polinomial es un modelo estadístico que busca predecir un valor continuo a partir de una o más variables independientes, extendiendo la regresión lineal al utilizar funciones polinómicas para modelar la relación entre las variables.

## Implementación del Modelo
El modelo permite cargar datos en formatos CSV o JSON, entrenar el modelo de regresión polinomial y hacer predicciones sobre nuevos datos. Los resultados se visualizan en gráficos y tablas.

## Parámetros Utilizados
| Parámetro          | Descripción                                        | Tipo       |
|--------------------|----------------------------------------------------|------------|
| degree             | Grado del polinomio a utilizar en el modelo       | int        |
| newXValue          | Valor de entrada para la predicción                | float      |

## Funciones Implementadas
### Función para procesar el contenido de un archivo CSV y extraer los valores de X e Y.
```javascript
function parseCSV(fileContent) {}
```
Función para procesar el contenido de un archivo JSON y extraer los valores de X e Y.
```javascript
function parseJSON(fileContent) {}
```
### Event Listener para el botón de carga de datos.
```javascript
document.getElementById('loadButton').addEventListener('click', function () { ... });
```
### Controlador de clic para el botón de entrenamiento.
```javascript
document.getElementById('trainButton').onclick = function () { ... };
```
### Controlador de clic para el botón de predicción.
```javascript
document.getElementById('predictButton').onclick = function () { ... };
```
### Controlador de clic para el botón de mostrar gráfico.
```javascript
document.getElementById('viewChartButton').onclick = function () { ... };
```

### Función que actualiza la tabla de datos con los valores de X y Y.
```javascript
function updateDataTables() {}
```
### Función que dibuja el gráfico de regresión polinomial utilizando Google Charts.
```javascript
function drawFullRegression() {}
```
### Función que actualiza la tabla de errores con los resultados de la predicción.
```javascript
function updateErrorTable(errors) {}
```
### Ejemplo de Datos de Entrada (JSON)
Un ejemplo de archivo JSON que puede ser utilizado para cargar los datos:

```json
[
    { "x": 1, "y": 1 },
    { "x": 2, "y": 4 },
    { "x": 3, "y": 9 },
    { "x": 4, "y": 16 },
    { "x": 5, "y": 25 }
]
```

## Resultados
Los resultados incluyen:

- La tabla con los valores de entrada X, los valores reales Y y las predicciones para cada grado del polinomio.
- Gráfico que representa la regresión polinomial y los datos.
---
## 3. Árbol de Decisión

## Descripción
El árbol de decisión es un modelo de aprendizaje automático que utiliza una estructura de árbol para tomar decisiones basadas en características de los datos. Se utiliza comúnmente para problemas de clasificación y regresión, dividiendo los datos en subconjuntos basados en preguntas sobre las características.

## Implementación del Modelo
Este modelo permite cargar datos desde archivos CSV o JSON, entrenar un árbol de decisión y realizar predicciones. También proporciona visualización del árbol entrenado.

## Parámetros Utilizados
| Parámetro         | Descripción                                          | Tipo       |
|-------------------|------------------------------------------------------|------------|
| fileInput         | Entrada para cargar archivos CSV o JSON              | File       |
| data              | Datos de entrada para realizar predicciones          | Array      |
| prediction        | Resultado de la predicción                            | String     |

## Funciones Implementadas
### Función para cargar datos desde un archivo CSV o JSON.
```javascript
function loadFileData(fileContent, fileType) {}
```
### Función para procesar el contenido de un archivo CSV y extraer los datos.
```javascript
function parseCSV(fileContent) {}
```
### Función para procesar el contenido de un archivo JSON y extraer los datos.
```javascript
function parseJSON(fileContent) {}
```
### Event Listener para el botón de carga de datos.
```javascript
document.getElementById('fileInput').addEventListener('change', function (event) { ... });
```
### Función para entrenar el modelo de árbol de decisión.
```javascript
document.getElementById('trainButton').onclick = function () { ... };
```
### Función para mostrar el árbol de decisión.
```javascript
document.getElementById('showTreeButton').onclick = function () { ... };
```
### Función que actualiza la tabla de datos.
```javascript
function updateTable(headers, data) {}
```
### Método para realizar predicciones con el modelo entrenado.
```javascript
document.getElementById('predict').onclick = function () { ... };
```
### Función para realizar la predicción y actualizar la visualización.
```javascript
const testWithChart = () => { ... };
```
### Ejemplo de Datos de Entrada (JSON)
Un ejemplo de archivo JSON que puede ser utilizado para cargar los datos:

```json
[
    { "feature1": "value1", "feature2": "value2", "label": "class1" },
    { "feature1": "value3", "feature2": "value4", "label": "class2" }
]
```
## Resultados
Los resultados incluyen:

- La tabla con los datos de entrenamiento y las predicciones realizadas por el modelo.
- Visualización del árbol de decisión, mostrando cómo se toman las decisiones basadas en los datos de entrada.
---
## 4. Redes Neuronales

## Descripción
El modelo de redes neuronales implementa un sistema que predice la relación entre dos números ingresados por el usuario. Este modelo utiliza dos redes neuronales separadas para realizar predicciones sobre:
1. La probabilidad de que dos números sean diferentes.
2. La probabilidad de que dos números sean iguales.

## Implementación del Modelo
El modelo permite al usuario ingresar dos números y proporciona la capacidad de realizar predicciones en función de esos números. La implementación utiliza JavaScript y la biblioteca `tytus.js`.

## Parámetros Utilizados
| Parámetro         | Descripción                                          | Tipo       |
|-------------------|------------------------------------------------------|------------|
| input1            | Primer número para la predicción                    | Number     |
| input2            | Segundo número para la predicción                   | Number     |
| Resultado         | Resultado de la predicción sobre números diferentes   | String     |
| input3            | Primer número para el Test 2                        | Number     |
| input4            | Segundo número para el Test 2                       | Number     |
| Resultado2        | Resultado de la predicción sobre números iguales      | String     |

## Funciones Implementadas
### Función para hacer la predicción sobre la diferencia de números.
```javascript
function makePrediction() {}
```
### Función para hacer la predicción sobre la igualdad de números.
```javascript
function makePrediction2() {}
```
### Entrenamiento de la red neuronal para el primer caso.
```javascript
for (let i = 0; i < 10000; i++) {}
```
### Entrenamiento de la red neuronal para el segundo caso.
```javascript
for (let i = 0; i < 10000; i++) {}
```
### Ejemplo de Datos de Entrada
No se requiere un formato específico de datos para este modelo, ya que se generan números aleatorios para el entrenamiento de las redes neuronales.

## Resultados
Los resultados incluyen:

- Probabilidad de que el primer número sea diferente del segundo: Muestra el resultado de la primera predicción.
- Probabilidad de que el primer número sea igual al segundo: Muestra el resultado de la segunda predicción.
---

## 5. Naive Bayes

## Descripción
Naive Bayes es un conjunto de algoritmos de clasificación basados en el teorema de Bayes, asumiendo la independencia entre las características. Es eficaz para problemas de clasificación donde la relación entre las características y la variable objetivo puede ser modelada de forma probabilística.

## Implementación del Modelo
Este modelo permite cargar datos desde archivos CSV o JSON, inicializar el clasificador Naive Bayes con los datos cargados, y realizar predicciones basadas en las condiciones definidas por el usuario. También proporciona una tabla para mostrar los datos de entrenamiento y una interfaz para la selección de variables.

## Parámetros Utilizados
| Parámetro          | Descripción                                              | Tipo            |
|--------------------|----------------------------------------------------------|-----------------|
| `fileInput`        | Entrada para cargar archivos CSV o JSON                  | File            |
| `targetVariable`   | Variable objetivo seleccionada para la predicción        | String          |
| `causes`           | Conjuntos de causas que afectan a la variable objetivo    | Array           |
| `prediction`       | Resultado de la predicción                               | Array           |

## Funciones Implementadas
### Event Listener para el botón de carga de datos.
```javascript
document.getElementById("loadButton").addEventListener("click", function () { ... });
```
### Función para inicializar el modelo Naive Bayes con los datos.
```javascript
function initializeNaiveBayes(data) { ... }
```
### Función para mostrar los datos en una tabla.
```javascript
function displayData(data) { ... }
```
### Función para realizar predicciones basadas en las causas y efectos seleccionados.
```javascript
function Predict() { ... }
```
### Ejemplo de Datos de Entrada (JSON)
Un ejemplo de archivo JSON que puede ser utilizado para cargar los datos:

```json
[
    { "feature1": "value1", "feature2": "value2", "label": "class1" },
    { "feature1": "value3", "feature2": "value4", "label": "class2" }
]
```
## Resultados
Los resultados incluyen:

- La tabla con los datos de entrenamiento.
- Un dropdown para seleccionar la variable objetivo (efecto).
- Un conjunto de selectores para definir las causas.
- Visualización del resultado de la predicción, mostrando tanto la clase como la probabilidad asociada.
---
## 6. K-Means

## Descripción
K-Means es un algoritmo de agrupamiento que clasifica un conjunto de datos en un número fijo de grupos (clusters). El objetivo es dividir los datos en grupos donde los elementos dentro de cada grupo son más similares entre sí que a los de otros grupos. Se basa en el cálculo de centroides que representan la media de los puntos en cada cluster.

## Implementación del Modelo
Este modelo permite cargar datos desde archivos CSV o JSON, inicializar el algoritmo K-Means con los datos cargados, y ejecutar la clasificación de los datos en clusters. La interfaz incluye opciones para cargar, limpiar datos y visualizar los resultados en una tabla y en un gráfico.

## Parámetros Utilizados
| Parámetro          | Descripción                                            | Tipo            |
|--------------------|--------------------------------------------------------|-----------------|
| `fileInput`        | Entrada para cargar archivos CSV o JSON                | File            |
| `data`             | Variable que almacena los datos cargados               | Array           |
| `loadLabel`        | Mensaje de estado que indica si los datos se cargaron correctamente | Elemento HTML   |
| `executeButton`    | Botón para ejecutar el algoritmo K-Means              | Button          |
| `clearButton`      | Botón para limpiar los datos y restablecer el estado inicial | Button          |
| `canvas`           | Elemento donde se dibujará el gráfico de clusters     | Canvas          |

## Funciones Implementadas
### Event Listener para el botón de carga de datos.
```javascript
document.getElementById("loadButton").addEventListener("click", function () { ... });
```
### Función para inicializar el modelo K-Means con los datos.
```javascript
const kmeans = new G8_Kmeans({ canvas: document.getElementById('grafica'), data: data, k: 4 });
```
### Función para mostrar los datos en una tabla.
```javascript
function displayClusterData(kmeans) { ... }
```
### Ejemplo de Datos de Entrada (JSON)
Un ejemplo de archivo JSON que puede ser utilizado para cargar los datos:

```json
[
    { "feature1": "value1", "feature2": "value2" },
    { "feature1": "value3", "feature2": "value4" }
]
```
## Resultados
Los resultados incluyen:

- Una tabla con la información de los centroides de cada cluster.
- Un gráfico que muestra la distribución de los datos en los diferentes clusters.
- Mensajes de estado que indican si los datos se cargaron correctamente o si se necesita cargar un archivo.
---
## 7. K-Nearest Neighbor

### Descripción
K-Nearest Neighbor (KNN) es un algoritmo de clasificación basado en la distancia, donde los puntos de datos son clasificados según la mayoría de sus vecinos más cercanos. Este método es efectivo para problemas de clasificación y regresión, y se basa en las distancias (como la distancia euclidiana y manhattan) entre los puntos de datos.

### Implementación del Modelo
Este modelo permite cargar datos desde archivos CSV o JSON, inicializar el clasificador KNN con los datos cargados, y realizar predicciones basadas en el punto definido por el usuario. También proporciona una tabla para mostrar los datos de entrenamiento y una interfaz para ingresar un punto a analizar.

### Parámetros Utilizados
| Parámetro         | Descripción                                                | Tipo            |
|-------------------|------------------------------------------------------------|-----------------|
| `fileInput`       | Entrada para cargar archivos CSV o JSON                    | File            |
| `pointInput`      | Punto definido por el usuario para análisis                | String          |
| `data`            | Conjunto de datos de entrenamiento                          | Array           |
| `euclidean`       | Resultado de la distancia euclidiana                       | Number          |
| `manhattan`       | Resultado de la distancia manhattan                        | Number          |

### Funciones Implementadas
#### Event Listener para el botón de carga de datos.
```javascript
document.getElementById("loadButton").addEventListener("click", function () { ... });
```
### Función para mostrar los datos en una tabla.
```javascript
function displayData(data) { ... }
```
### Evento para ejecutar KNN y calcular distancias.
```javascript
document.getElementById("executeButton").addEventListener("click", function () { ... });
```
### Función para mostrar el punto analizado.
```javascript
function displayPoint(point) { ... }
```
### Evento para ver la gráfica.
```javascript
document.getElementById("viewChartButton").addEventListener("click", function () { ... });
```
### Función para graficar los puntos.
```javascript
function drawChart(data, point) { ... }
```
### Ejemplo de Datos de Entrada (JSON)
Un ejemplo de archivo JSON que puede ser utilizado para cargar los datos:

```json
[
    { "feature1": "value1", "feature2": "value2", "group": "N" },
    { "feature1": "value3", "feature2": "value4", "group": "P" }
]
```
## Resultados
Los resultados incluyen:

- La tabla con los datos de entrenamiento.
- Un campo de entrada para el punto a analizar (en formato X,Y).
- Resultados de las distancias calculadas (euclidiana y manhattan).
- Visualización del resultado en forma de gráfico, mostrando los puntos y el punto analizado.
