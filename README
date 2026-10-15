# Análisis de Comportamiento de Clientes - ConnectaTel

## Objetivo del Proyecto
El presente proyecto tiene como objetivo evaluar el comportamiento de los clientes de la empresa de telecomunicaciones ConnectaTel en Latinoamérica, utilizando registros históricos consolidados hasta el año 2024. A través de la limpieza de datos, el cálculo de métricas de consumo y la segmentación demográfica y operativa, se busca identificar patrones de uso, detectar valores atípicos (heavy users) y generar recomendaciones estratégicas basadas en datos para optimizar la retención de clientes y mejorar la oferta comercial de los planes Básico y Premium.

## Datasets Utilizados
El análisis se fundamenta en la integración de tres conjuntos de datos (en formato CSV):
*   **`plans.csv`**: Contiene la información paramétrica de los planes comerciales actuales, incluyendo precios base, cuotas de minutos, mensajes y gigabytes incluidos, así como las tarifas por consumo excedente.
*   **`users_latam.csv`**: Registra la información demográfica y de estado de cuenta de 4,000 clientes, abarcando identificadores únicos, edad, ciudad, fecha de alta (`reg_date`), tipo de plan suscrito y fecha de cancelación (`churn_date`) en caso de abandono.
*   **`usage.csv`**: Almacena el detalle transaccional del uso real de los servicios (40,000 registros), tipificando cada evento como llamada (`call`) o mensaje (`text`), junto con su fecha, duración en minutos o longitud en caracteres.

## Etapas del Análisis Realizadas
El flujo de trabajo analítico se estructuró en las siguientes fases metodológicas:
1.  **Carga y Exploración Inicial:** Importación de librerías y revisión de la estructura tabular, tipos de datos y recuento de valores faltantes.
2.  **Identificación y Tratamiento de Anomalías:** Detección de valores centinela (como edades de -999 y ciudades marcadas con `?`) y su respectiva imputación estadística o estandarización a valores nulos lógicos.
3.  **Estandarización Temporal:** Filtrado paramétrico para aislar y anular inconsistencias cronológicas (fechas de registro proyectadas al año 2026), limitando el espectro de análisis al horizonte de negocio establecido (2024).
4.  **Agregación de Tráfico por Usuario:** Transformación de la tabla de eventos transaccionales en un perfil consolidado por cliente, sumando la cantidad de mensajes, llamadas y minutos consumidos.
5.  **Detección de Valores Atípicos:** Cálculo del Rango Intercuartílico (IQR) para identificar usuarios con consumos extremos superiores y argumentación técnica sobre su conservación para prevenir sesgos de truncamiento.
6.  **Segmentación de Clientes:** Clasificación multidimensional de la base de usuarios mediante la creación de variables derivadas, categorizando por grupo etario (Joven, Adulto, Adulto Mayor) y por intensidad de tráfico (Bajo uso, Uso medio, Alto uso).
7.  **Insight Ejecutivo:** Redacción de hallazgos estadísticos y recomendaciones accionables para los tomadores de decisión (stakeholders).

## Cómo Ejecutar el Notebook
Este proyecto está contenido en un entorno de Jupyter Notebook (`.ipynb`). Para visualizarlo e interactuar con el código, se recomiendan las siguientes opciones:

**Opción A: Ejecución en la Nube (Google Colab)**
1.  Descarga el archivo `.ipynb` de este repositorio.
2.  Accede a [Google Colab](https://colab.research.google.com/).
3.  Selecciona `Archivo` > `Subir notebook` y carga el archivo descargado.
4.  Asegúrate de cargar las carpetas de los datasets en el entorno virtual de Colab o ajustar las rutas de lectura en la primera celda a la ubicación correspondiente de los archivos CSV.

**Opción B: Ejecución Local**
1.  Clona el repositorio en tu máquina local.
2.  Abre una terminal o línea de comandos en el directorio del proyecto.
3.  Inicia el entorno ejecutando el comando: `jupyter notebook` o `jupyter lab`.
4.  Selecciona el archivo del proyecto en tu navegador para abrirlo.

## Guía de Reproducción
Para garantizar la reproducibilidad exacta de los resultados y gráficos presentados en este estudio, sigue estos pasos:
1.  **Requisitos previos:** Asegúrate de tener instalado Python 3.8+ y las librerías base necesarias (`pandas`, `matplotlib`, `seaborn` y `numpy`).
2.  **Rutas de archivos:** El cuaderno asume que los archivos CSV se encuentran en un directorio local llamado `/datasets/`. Si descargas el proyecto, verifica que esta estructura de carpetas se mantenga o modifica las sentencias `pd.read_csv()` en el Paso 1 para que apunten a la ruta correcta de tus archivos extraídos.
3.  **Ejecución secuencial:** El cuaderno está diseñado para ejecutarse de manera lineal. Utiliza la opción *Run All* (Ejecutar todo) o procesa las celdas secuencialmente de arriba hacia abajo, ya que las variables de perfilado y segmentación dependen del preprocesamiento y limpieza ejecutados en las celdas iniciales.
