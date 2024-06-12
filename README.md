# MCDA-Proyecto-20241-Anomalias_Contables
Este repositorio contiene todo el analisis realizado para la identificación de anomalias contables para una entidad financiera

Versión de python 3.11.7

# Detección de Anomalías en Registros Contables

## Entendimiento del Problema

El sector financiero colombiano se compone por establecimientos de crédito, entidades de servicios financieros, sociedades de capitalización, aseguradoras y sus derivados, entre otros.

Dentro del grupo de establecimientos de crédito o EC, los bancos son los más conocidos por la comunidad en general. Los modelos de fraude son bastante conocidos e implementados; sin embargo, actualmente los departamentos contables, a pesar de sus exhaustivas auditorías, a menudo requieren de un proceso de detección de anomalías que vaya más allá de la verificación del saldo actual versus el saldo anterior, de modo que permita conocer de primera mano todos aquellos movimientos atípicos que se registran durante determinado periodo contable, usando los datos y modelos estadísticos y computacionales para dicha actividad.

El problema requiere identificar las anomalías en registros contables de gastos que no pueden ser detectados durante el proceso de razonabilidad y que se identifiquen dentro de algún tipo de anomalías: de magnitud, de tiempo o de primeras veces. El modelo debe evitar los falsos negativos y, a su vez, ser escalable en tiempo.

## Impacto de la Solución

Con la implementación de un modelo que detecte anomalías o outliers en el registro contable, la organización financiera podría detectar de forma temprana algunas irregularidades financieras que pueden ser omitidas dentro del proceso de razonabilidad.

Por otro lado, con la automatización, el modelo puede ayudar a agilizar el proceso contable al identificar de manera rápida y precisa las transacciones que requieren una revisión adicional, reduciendo en cierta parte el error humano y permitiendo que el equipo se centre en otras tareas más estratégicas y suponga de fondo una optimización de recursos humanos y tecnológicos.


## Archivos

- `Analisis_Exploratorio.ipynb`: Jupyter Notebook que contiene el análisis exploratorio de los datos compartidos para la detección de anomalias contables.
- `Analisis_MCA.ipynb`: Jupyter Notebook que contiene el análisis realizado através de analisis de correspondencia multiple.
- `Análisis_PCA.ipynb`: Jupyter Notebook que contiene el análisis realizado através de analisis de componentes principales.

### Teoría de los Modelos Usados
#### 1. Análisis de correspondencia multiple:
Con este modelo, se busca convertir, a través del Análisis de Correspondencia Múltiple (MCA), las variables categóricas en una representación numérica. MCA es una técnica estadística multivariada de reducción de información que se utiliza para analizar tablas de contingencia en múltiples dimensiones. Su objetivo principal es examinar la asociación entre las categorías de más de dos variables cualitativas, lo cual se busca hacer con esta información.

#### 2. Análisis de componentes principales:
El Análisis de Componentes Principales (PCA) permite reducir la dimensionalidad de una matriz de datos 𝑛×𝑝, donde 𝑛 representa la cantidad de registros y 𝑝 la cantidad de variables.

## Cómo visualizar el archivo `.ipynb`

Para visualizar el archivo `.ipynb`, puedes utilizar [Jupyter Notebook](https://jupyter.org/) o [Google Colab](https://colab.research.google.com/):

### Usando Jupyter Notebook

1. Instala Jupyter Notebook si no lo tienes:
   ```sh
   pip install notebook

