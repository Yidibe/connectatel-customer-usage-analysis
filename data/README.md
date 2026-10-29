# ConnectaTel — Datasets

Esta carpeta contiene los tres archivos CSV utilizados para el análisis de patrones de consumo y segmentación de clientes de ConnectaTel.

## Archivos utilizados

- **users_latam.csv:** contiene información de 4,000 clientes, incluyendo identificador, edad, ciudad, plan contratado y fechas de registro o baja.
- **usage.csv:** contiene 40,000 registros de llamadas y mensajes, incluyendo fechas, duración de llamadas y longitud de mensajes.
- **plans.csv:** contiene información de los dos planes comerciales, sus beneficios y tarifas.

## Propósito

Estos datasets permiten realizar la limpieza de datos, el análisis estadístico, la detección de valores atípicos mediante IQR y la segmentación de clientes por edad y nivel de uso.

El análisis completo se encuentra en `notebooks/connectatel-customer-usage-analysis.ipynb`.
