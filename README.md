# Retail Sales Analysis

Proyecto de análisis de ventas de una tienda de retail utilizando Python y NumPy.

Este proyecto corresponde a una actividad práctica de ciencia de datos, cuyo objetivo principal es realizar una primera exploración y manipulación de un dataset de ventas retail. En esta etapa se trabaja principalmente con NumPy para cargar datos desde un archivo CSV, realizar un preprocesamiento básico y obtener estadísticas iniciales por categoría de producto.

---

## Descripción del Proyecto

El proyecto analiza un conjunto de datos de ventas de una tienda de retail. El dataset contiene información sobre transacciones, clientes, categorías de productos, cantidades vendidas, precios unitarios y montos totales de venta.

A partir de estos datos, se realizan operaciones básicas de análisis para comprender el comportamiento general de las ventas y obtener información relevante, como:

- Total de ventas por categoría de producto.
- Promedio de ventas por categoría.
- Categoría con mayor volumen de ventas.
- Categoría con menor volumen de ventas.
- Filtrado de ventas por una categoría específica.
- Cálculo de estadísticas generales utilizando operaciones matemáticas con NumPy.

---

## Objetivo General

Aplicar herramientas básicas de análisis de datos con NumPy para explorar, limpiar y analizar un dataset de ventas retail.

---

## Objetivos Específicos

- Cargar un archivo CSV utilizando NumPy.
- Revisar la estructura general del dataset.
- Identificar las columnas disponibles.
- Realizar un preprocesamiento básico de los datos.
- Calcular ventas totales por categoría de producto.
- Calcular el promedio de ventas por categoría.
- Identificar la categoría con mayor y menor venta.
- Filtrar registros según una categoría específica.
- Aplicar operaciones matemáticas como suma, resta, multiplicación y división para obtener estadísticas adicionales.

---

## Dataset

El dataset utilizado corresponde a un archivo CSV llamado:

```text
retail_sales_dataset.csv

```

# Documentación del Análisis parte 3

En esta sección se documenta cada paso realizado durante la transformación y análisis avanzado del dataset de ventas retail. El objetivo principal es explicar qué se hizo en cada etapa y por qué fue necesario hacerlo.

---

## 1. Carga del dataset

Se cargó el archivo `retail_sales_dataset.csv` utilizando la librería Pandas.

Este paso es necesario porque Pandas permite trabajar con datos en forma de tabla mediante un DataFrame, facilitando la exploración, transformación y análisis de la información.

---

## 2. Revisión inicial de los datos

Se revisaron las primeras filas del dataset con `head()`, la estructura general con `info()`, los nombres de las columnas con `columns` y la existencia de valores nulos con `isnull().sum()`.

Esto se realizó para comprender la estructura del archivo, verificar qué columnas estaban disponibles y confirmar si existían datos faltantes que pudieran afectar el análisis.

---

## 3. Conversión de la columna Date

La columna `Date` fue convertida a formato de fecha utilizando `pd.to_datetime()`.

Este paso es importante porque permite trabajar correctamente con fechas y extraer información útil, como el mes y el año de cada venta.

---

## 4. Creación de nuevas columnas de tiempo

Se crearon las columnas `Month` y `Year` a partir de la columna `Date`.

Estas nuevas columnas permiten analizar las ventas según el periodo en que ocurrieron, por ejemplo, comparar ventas por mes o por año.

---

## 5. Creación de la columna Calculated Total

Se creó la columna `Calculated Total`, multiplicando la cantidad vendida por el precio unitario:

`Quantity * Price per Unit`

Aunque el dataset ya contiene la columna `Total Amount`, esta nueva columna permite comprobar y practicar el cálculo del ingreso total por venta usando columnas existentes.

---

## 6. Normalización de las ventas

Se creó la columna `Normalized Sales`, que transforma los valores de `Total Amount` a una escala entre 0 y 1.

Esto se hizo para facilitar la comparación entre ventas de distintos montos, especialmente cuando existen valores pequeños y grandes dentro de la misma columna.

---

## 7. Clasificación de las ventas

Se creó la columna `Sales Category`, que clasifica cada venta en tres categorías:

- `Alta`: ventas desde 1000 hacia arriba.
- `Media`: ventas desde 500 hasta 999.
- `Baja`: ventas menores a 500.

Esta clasificación permite analizar las ventas de una forma más simple y comprensible, separando las transacciones según su nivel de ingreso.

Los valores fueron definidos considerando que la columna `Total Amount` tiene montos aproximados entre 25 y 2000.

---

## 8. Agrupación por categoría de producto

Se agruparon los datos por `Product Category` y se sumó la columna `Total Amount`.

Esto permite identificar qué categorías de productos generan mayores ingresos dentro del dataset.

---

## 9. Agrupación por categoría de producto y mes

Se realizó una agrupación por dos columnas: `Product Category` y `Month`.

Este análisis permite observar cómo se comportan las ventas de cada categoría de producto a lo largo de los meses.

---

## 10. Aplicación de funciones de agregación

Se aplicaron funciones estadísticas como:

- `sum`: suma total de ventas.
- `mean`: promedio de ventas.
- `count`: cantidad de registros.
- `min`: valor mínimo.
- `max`: valor máximo.
- `std`: desviación estándar.
- `var`: varianza.

Estas funciones permiten obtener una descripción más completa del comportamiento de las ventas por grupo.

---

## 11. Agrupación por género y categoría de producto

Se agruparon los datos por `Gender` y `Product Category`.

Este paso permite analizar si existen diferencias en el comportamiento de compra según el género y la categoría de producto.

---

## 12. Agrupación por categoría de venta

Se agruparon los datos según la columna `Sales Category`.

Esto permite conocer cuántas ventas fueron clasificadas como altas, medias o bajas, además de analizar el monto total y promedio de cada grupo.

---

## 13. Comparación de cada venta con el promedio general

Se calculó el promedio general de la columna `Total Amount` y luego se creó una función personalizada para indicar si cada venta está sobre, bajo o igual al promedio.

Este análisis ayuda a identificar rápidamente qué ventas tienen un comportamiento superior o inferior al promedio general del dataset.

---

## 14. Cálculo de la media por grupo

Se calculó el promedio de ventas para cada `Product Category` usando `groupby()` junto con `transform("mean")`.

Este paso permite obtener el promedio correspondiente a la categoría de producto de cada fila, sin perder la estructura original del DataFrame.

---

## 15. Desviación respecto a la media del grupo

Se creó la columna `Deviation From Group Mean`, restando el promedio de la categoría al valor de cada venta:

`Total Amount - Group Average`

Esto permite saber si una venta fue mayor o menor que el promedio de su propia categoría de producto.

---

## 16. Interpretación de la desviación

Se creó una función personalizada con `apply()` para interpretar la desviación de cada venta.

La columna resultante indica si la venta fue:

- Mayor que el promedio de su categoría.
- Menor que el promedio de su categoría.
- Igual al promedio de su categoría.

Este paso facilita la lectura del análisis, ya que transforma un valor numérico en una interpretación más clara.

---

## 17. Guardado del dataset transformado

Finalmente, se guardó el dataset transformado en un nuevo archivo llamado `retail_sales_transformado.csv`.

Esto permite conservar las nuevas columnas creadas y utilizar el archivo resultante en futuros análisis o modelos predictivos.

---

# Conclusión

Durante este análisis se aplicaron técnicas de transformación y análisis avanzado de datos con Pandas. Se crearon nuevas columnas útiles, se normalizaron las ventas, se clasificaron los montos en categorías y se realizaron agrupaciones con distintas funciones de agregación.

Además, se utilizó el método `apply()` para aplicar funciones personalizadas y facilitar la interpretación de los resultados. Gracias a estos pasos, el dataset quedó mejor preparado para obtener insights y continuar con futuros análisis o modelos de predicción.