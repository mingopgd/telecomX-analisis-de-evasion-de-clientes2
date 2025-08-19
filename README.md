# Telecom X - Parte 2

Este proyecto tiene como objetivo principal predecir la cancelación de clientes (churn) utilizando datos de servicios contratados y características demográficas. El análisis permite identificar los factores que más influyen en la decisión de los clientes de dejar el servicio.

Estructura del proyecto:
- `TelecomX_Data_Limpio.csv`: dataset original limpio.
- `TelecomX_Data_Limpio_Optimizado.csv`: dataset preprocesado y codificado.
- Cuaderno principal con análisis exploratorio, visualizaciones y modelado.
- Carpeta opcional con gráficos generados durante el análisis.

Preparación de datos:
- Clasificación de variables en categóricas y numéricas.
- One-hot encoding aplicado a variables categóricas.
- Reconstrucción aproximada del gasto total usando servicios activos.
- Separación en conjuntos de entrenamiento y prueba.
- Normalización aplicada solo a modelos sensibles a la escala (Regresión Logística, KNN).

Modelado y evaluación:
- Modelos utilizados: Regresión Logística y Random Forest.
- Métricas: Accuracy, Precision, Recall, F1-score y matriz de confusión.
- Análisis de importancia de variables para identificar factores relevantes en la cancelación.

Conclusión:
Los resultados muestran que variables como tipo de contrato, uso de servicios de internet y métodos de pago influyen significativamente en la predicción de churn. Esto permite diseñar estrategias de retención focalizadas, como incentivos para clientes con contratos cortos o recomendaciones personalizadas según el uso de servicios.

Ejecución:
1. Instalar librerías: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.
2. Cargar dataset optimizado: `TelecomX_Data_Limpio_Optimizado.csv`.
3. Ejecutar el cuaderno principal para reproducir gráficos, modelos y análisis.
