# MCDA-Proyecto-20241-Anomalias_Contables
Este repositorio contiene todo el analisis realizado para la identificación de anomalias contables para una entidad financiera

Versión de python 3.11.7
Libreria y sus versiones en archivo `requirements.txt`

# Detección de Anomalías en Registros Contables

## Entendimiento del Problema

El sector financiero colombiano se compone por establecimientos de crédito, entidades de servicios financieros, sociedades de capitalización, aseguradoras y sus derivados, entre otros.

Dentro del grupo de establecimientos de crédito o EC, los bancos son los más conocidos por la comunidad en general. Los modelos de fraude son bastante conocidos e implementados; sin embargo, actualmente los departamentos contables, a pesar de sus exhaustivas auditorías, a menudo requieren de un proceso de detección de anomalías que vaya más allá de la verificación del saldo actual versus el saldo anterior, de modo que permita conocer de primera mano todos aquellos movimientos atípicos que se registran durante determinado periodo contable, usando los datos y modelos estadísticos y computacionales para dicha actividad.

El problema requiere identificar las anomalías en registros contables de gastos que no pueden ser detectados durante el proceso de razonabilidad contable. El modelo debe evitar los falsos negativos y, a su vez, ser escalable en tiempo.

## Impacto de la Solución

Con la implementación de un modelo que detecte anomalías o outliers en el registro contable, la organización financiera podría detectar de forma temprana algunas irregularidades financieras que pueden ser omitidas dentro del proceso de razonabilidad.

Por otro lado, con la automatización, el modelo puede ayudar a agilizar el proceso contable al identificar de manera rápida y precisa las transacciones que requieren una revisión adicional, reduciendo en cierta parte el error humano y permitiendo que el equipo se centre en otras tareas más estratégicas y suponga de fondo una optimización de recursos humanos y tecnológicos.


## Archivos

- `Analisis_Exploratorio.ipynb`: Jupyter Notebook que contiene el análisis exploratorio de los datos compartidos para la detección de anomalias contables.
- `Analisis_MCA.ipynb`: Jupyter Notebook que contiene el análisis realizado através de analisis de correspondencia multiple.
- `Análisis_PCA.ipynb`: Jupyter Notebook que contiene el análisis realizado através de analisis de componentes principales.
- `Modelos_LR_KNN.ipynb`: Jupyter Notebook que contiene el proceso realizado para entrenar, validar y clasificar registros atipicos através de KNN y Regresión Lineal.
- `Modelo_Distancias.ipynb`: Jupyter Notebook que contiene el proceso realizado para calculo de distancias e identificar atipicos.
- `Consolidacion_Modelos.ipynb`: Jupyter Notebook encargado que consolidar las salidas de los modelos "KNN-LR" y "Distancias"
- `Orquestador_Notebook.ipynb`: Jupyter Notebook encargado de orquestar la ejecución de los procesos en caso de que se requiera.
- `requirements.txt`: Archivo con librerias usadas y sus versiones
- `query_3ec5aea3_20240410T153703.zip`: Base para ejecución inicial. Debe descomprimirse


### Teoría de los Modelos Usados
#### 1. Análisis de correspondencia multiple:
Con este modelo, se busca convertir, a través del Análisis de Correspondencia Múltiple (MCA), las variables categóricas en una representación numérica. MCA es una técnica estadística multivariada de reducción de información que se utiliza para analizar tablas de contingencia en múltiples dimensiones. Su objetivo principal es examinar la asociación entre las categorías de más de dos variables cualitativas, lo cual se busca hacer con esta información.

#### 2. Análisis de componentes principales:
El Análisis de Componentes Principales (PCA) permite reducir la dimensionalidad de una matriz de datos 𝑛×𝑝, donde 𝑛 representa la cantidad de registros y 𝑝 la cantidad de variables.

#### 3. KNN y Regresión Lineal:
-	K-Nearest Neighbors (KNN): Busca identificar los 'K' vecinos más cercanos a cada punto en el espacio de características. El valor de 'K' es un hiperparámetro crucial que, dependiendo de su tamaño, puede generar comportamientos más suavizados o más específicos. Un valor pequeño de 'K' puede hacer que el modelo sea sensible al ruido en los datos, mientras que un valor grande de 'K' puede resultar en una mayor generalización y suavización de las predicciones.
-	Regresión Lineal: se asume que existe una relación lineal entre la variable gasto_ejecutado y las variables independientes categóricas, las cuales se transforman en variables dummies. Para ello, se particiona el conjunto de datos según la variable nivel_1_cuenta y se evalúa un modelo para cada categoría, asumiendo que los datos que tomen el mismo valor en esta variable están relacionados entre sí.

#### 4. Distancias:

- Distancia Euclidiana: Permite calcular la distancia entre 2 puntos en el espacio, para el cual se define un centroide que toma el valor de la media de los datos del gasto_ejecutado (µ). Para todos los registros del conjunto de datos se procede entonces a calcular la distancia respecto a le media de la siguiente forma:
	
								d= √(〖(x-μ)〗^2 )

- Distancia de Manhatan: Igual que para la distancia euclidiana, se define el centroide con la media de la variable gasto_ejecutado y se calcula la distancia con la siguiente formula:

								d=|x-μ|

- Distancia a la Mediana: Para esta métrica, en lugar de la media, se utiliza la mediana como centroide para calcular distancias, lo cual podría ser más robusto ante la presencia de outliers, ya que la mediana no se ve tan afectada por valores extremos como la media. Se procede entonces a calcular la distancia de la siguiente forma:

								d=|x-Μ|

Siendo Μ la media del gasto_ejecutado

## Para la ejecución del proyecto

Existen 2 maneras de reproducir el código según tu necesidad:

1. Ejecución notebook por notebook:
   - Si quieres ejecutar uno a uno de los notebooks debes:
   1. Instalar archivo requeriments.txt adjunto a este proyecto en la versión de python indicada.
   2. Verificar que exista la base origen `query_3ec5aea3_20240410T153703.csv` (Debe descomprimirse)
   3. Llevar el siguiente orden de ejecución:
      1. `Analisis_Exploratorio.ipynb`. (Opcional)
      2. `Modelo_Distancias.ipynb`. (Obligatorio) *La salida de este modelo es entrada para los siguientes procesos
      3. `Analisis_MCA.ipynb`. (Opcional)
      4. `Análisis_PCA.ipynb`. (Opcional)
      5. `Modelos_LR_KNN.ipynb`. (Obligatorio)
      6. `Consolidacion_Modelos.ipynb`. (Obligatorio)
     
2. Ejecución por orquestador:
   - Si sólo quieres ver la ejecución puntual de los modelos que detectan los outliers debes:
   1. Instalar archivo requeriments.txt adjunto a este proyecto en la versión de python indicada.
   2. Verificar que exista la base origen `query_3ec5aea3_20240410T153703.csv` (Debe descomprimirse)
   3. Descargar los jupyter notebooks adjuntos a este proyecto.
   4. Ejecutar `Orquestador_Notebook.ipynb`: Este notebook se encargará de ejecutar `Modelo_Distancias.ipynb`, `Modelos_LR_KNN.ipynb` y `Consolidacion_Modelos.ipynb`.

## Cómo visualizar el archivo `.ipynb`

Para visualizar el archivo `.ipynb`, puedes utilizar [Jupyter Notebook](https://jupyter.org/) o [Google Colab](https://colab.research.google.com/):

### Usando Jupyter Notebook

1. Instala Jupyter Notebook si no lo tienes:
   ```sh
   pip install notebook
   
## Cómo instalar archivo `requirements.txt`

1. Crea un entorno virtual:
    ```sh
    python -m venv venv
    ```

2. Activa el entorno virtual:

    - En Windows:
        ```sh
        venv\Scripts\activate
        ```

    - En macOS y Linux:
        ```sh
        source venv/bin/activate
        ```

3. Instala las dependencias:
    ```sh
    pip install -r requirements.txt
    ```

