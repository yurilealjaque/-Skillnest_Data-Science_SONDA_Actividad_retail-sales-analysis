
| Categoría | Nombre | ¿Lleva `()`? | Descripción |
| :--- | :--- | :---: | :--- |
| **Atributo** | `.shape` | No | Retorna una tupla con el número de filas y columnas. |
| **Atributo** | `.columns` | No | Lista las etiquetas de las columnas del DataFrame. |
| **Atributo** | `.index` | No | Retorna las etiquetas de las filas (el índice). |
| **Atributo** | `.dtypes` | No | Muestra el tipo de dato de cada columna. |
| **Atributo** | `.size` | No | Número total de elementos (filas × columnas). |
| **Atributo** | `.values` | No | Devuelve los datos como un arreglo de NumPy. |
| **Atributo** | `.ndim` | No | Número de dimensiones del objeto (2 para DataFrames). |
| **Atributo** | `.T` | No | Transpone el DataFrame (intercambia filas por columnas). |
| **Método (Vista)** | `.head(n)` / `.tail(n)` | **Sí** | Muestra las primeras o últimas *n* filas. |
| **Método (Info)** | `.info()` | **Sí** | Resumen de tipos, valores no nulos y uso de memoria. |
| **Método (Estad.)** | `.describe()` | **Sí** | Genera estadísticas descriptivas (media, std, min, etc.). |
| **Método (Estad.)** | `.mean()` / `.sum()` | **Sí** | Calcula el promedio o la suma de los valores. |
| **Método (Limp.)** | `.dropna()` | **Sí** | Elimina filas o columnas con valores faltantes. |
| **Método (Limp.)** | `.fillna(v)` | **Sí** | Reemplaza valores nulos con un valor específico *v*. |
| **Método (Selec.)** | `.loc[]` / `.iloc[]` | **No*** | Selección por etiquetas o por posición entera. |
| **Método (Trans.)** | `.apply(f)` | **Sí** | Aplica una función *f* a lo largo de un eje. |
| **Método (Agreg.)** | `.groupby()` | **Sí** | Agrupa datos para realizar operaciones por categorías. |
| **Función (I/O)** | `pd.read_csv()` | **Sí** | Carga datos desde un archivo CSV a un DataFrame. |
| **Función (I/O)** | `pd.read_excel()` | **Sí** | Carga datos desde un archivo de Excel. |
| **Función (Comb.)** | `pd.concat()` | **Sí** | Combina múltiples objetos de Pandas en uno solo. |
| **Función (Comb.)** | `pd.merge()` | **Sí** | Une DataFrames usando una lógica similar a SQL (joins). |

*\*Nota: `.loc` e `.iloc` utilizan corchetes `[]` por ser indexadores.*