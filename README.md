## ConnectaTel | Análisis de patrones de uso y segmentación de clientes

## Descripción del proyecto
ConnectaTel es una empresa de telecomunicaciones con operaciones en México y Colombia. Este proyecto analiza el comportamiento de sus clientes a partir de registros de llamadas y mensajes, con el propósito de identificar patrones de consumo, detectar valores atípicos (outliers) y reconocer segmentos con necesidades diferenciadas.

El análisis forma parte del bootcamp de Data Analyst de TripleTen y busca convertir los resultados estadísticos en recomendaciones útiles para mejorar la oferta comercial y la experiencia del cliente.

## Objetivos
- Explorar e integrar información de clientes, actividad y planes comerciales.
- Identificar y tratar problemas de calidad de datos.
- Describir el consumo mediante medias, medianas, percentiles y distribuciones.
- Detectar valores atípicos con histogramas, diagramas de caja y el método IQR.
- Segmentar clientes por edad y nivel de uso.
- Proponer oportunidades de fidelización y personalización de planes basadas en evidencia.

## Datasets utilizados
Archivo	Registros originales:

## Contenido principal
- users_latam.csv	4,000	Identificador de usuario, edad, ciudad, fecha de registro, plan contratado y fecha de baja.
- usage.csv	40,000	Actividad de llamadas y mensajes, fecha, duración y longitud del mensaje.
- plans.csv	2	Planes comerciales, precios, beneficios incluidos y tarifas por consumo adicional.

Los tres archivos se encuentran en la carpeta data/ de la estructura sugerida más abajo. Los registros de actividad corresponden al período de análisis de 2024.

## Etapas del análisis
1. Carga y exploración: lectura de archivos CSV; revisión de dimensiones, tipos de datos y estadísticas iniciales.
2. Diagnóstico de calidad: identificación de valores ausentes, valores centinela y fechas inconsistentes.
3. Limpieza y transformación: aplicación de reglas de limpieza reproducibles; tratamiento de edades inválidas, ciudades desconocidas y fechas; conservación de nulos estructurales asociados a distintos tipos de actividad.
4. Integración y agregación: consolidación de llamadas, mensajes y minutos por usuario; construcción del DataFrame user_profile.
5. Análisis descriptivo: cálculo de media, mediana, cuartiles y máximos; exploración de distribuciones mediante histogramas.
6. Detección de outliers: elaboración de boxplots y cálculo de límites superiores con el método IQR.
7. Segmentación: clasificación de clientes por edad (Joven, Adulto, Adulto Mayor) y nivel de uso (Bajo uso, Uso medio, Alto uso); visualización mediante gráficos de barras.
8. Conclusiones ejecutivas: interpretación de los resultados y formulación de recomendaciones comerciales.

## Hallazgos destacados
- La mayor parte de los usuarios se concentra en el segmento de Uso medio.
- Los consumos de llamadas, mensajes y especialmente minutos muestran distribuciones asimétricas hacia la derecha.
- El método IQR identificó 46 valores atípicos en mensajes, 30 en llamadas y 109 en minutos acumulados, por encima de los límites superiores de 11.5, 10.5 y 61.8575, respectivamente.
- Los valores atípicos se conservaron para el análisis, porque podrían representar patrones reales de consumo intensivo; no se consideraron errores automáticamente.
Alcance: las métricas de actividad son acumuladas por usuario durante el período analizado. No deben interpretarse como consumos mensuales sin una agregación adicional. La rentabilidad de los segmentos requiere validar ingresos y costos.

## Herramientas
- Python 3
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab

## Estructura sugerida del repositorio
connectatel-customer-usage-analysis/
├── README.md
├── notebooks/
│   └── connectatel-customer-usage-analysis.ipynb
└── data/
    ├── users_latam.csv
    ├── usage.csv
    └── plans.csv

## Cómo ejecutar el notebook en Google Colab
1. Descarga o clona este repositorio.
2. Abre Google Colab.
3. Selecciona Archivo > Subir notebook y abre connectatel-customer-usage-analysis.ipynb desde la carpeta notebooks/.
4. En el panel lateral Archivos de Google Colab, selecciona Subir y carga estos tres archivos de datos obligatorios desde la carpeta data/ del repositorio:
   - users_latam.csv: información de los clientes (edad, ciudad, plan y fechas de registro o baja).
   - usage.csv: registros de llamadas y mensajes (tipo de actividad, duración y fecha).
   - plans.csv: características, beneficios y tarifas de los planes comerciales.
     Los tres archivos deben estar cargados antes de ejecutar las celdas de lectura de datos.
5. Si los archivos se cargaron en /content/, usa rutas como estas:

import pandas as pd

users = pd.read_csv('/content/users_latam.csv')
usage = pd.read_csv('/content/usage.csv')
plans = pd.read_csv('/content/plans.csv')

6. Ejecuta las celdas en orden, desde la importación de librerías hasta las conclusiones ejecutivas, mediante Entorno de ejecución > Ejecutar todo.
Nota: los archivos cargados directamente en una sesión de Colab pueden desaparecer al reiniciar el entorno; vuelve a subirlos si es necesario.

## Guía breve de reproducción
1. Verifica que los archivos CSV estén disponibles y que sus rutas coincidan con las del notebook.
2. Ejecuta la exploración inicial y comprueba que los archivos contengan 4,000 clientes, 40,000 registros de uso y 2 planes.
3. Ejecuta las transformaciones de limpieza y la agregación por user_id.
4. Genera las estadísticas descriptivas, histogramas y boxplots.
5. Recalcula los límites IQR y las segmentaciones, y compara los resultados con los hallazgos documentados.
6. Revisa las conclusiones ejecutivas y confirma que correspondan a los resultados obtenidos.

## Próximos pasos
Contrastar los segmentos con las características de los planes Básico y Premium, analizar el consumo mensual y evaluar ingresos, costos y retención para fundamentar futuras decisiones comerciales.

