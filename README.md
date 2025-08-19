# Telecom X - Parte 2

## 📌 Propósito del proyecto
El objetivo principal de este análisis es **predecir el churn (cancelación) de clientes** de la empresa Telecom X, identificando las variables que más influyen en la decisión de cancelar el servicio. Esto permite proponer estrategias de retención y mejorar la fidelización de clientes.

---

## 🗂 Estructura del proyecto
El proyecto se organiza de la siguiente manera:

TelecomX-Parte2/
│
├── TelecomX_Data_Limpio.csv # Dataset original limpio
├── TelecomX_Data_Limpio_Optimizado.csv # Dataset preprocesado y optimizado
├── TelecomX_Churn_Analysis.ipynb # Cuaderno principal con todo el análisis y modelado
├── visualizaciones/ # Carpeta con gráficos generados (correlaciones, boxplots, importancia de variables)
│ ├── correlacion.png
│ ├── gasto_vs_churn.png
│ └── importancia_variables.png
└── README.md # Este archivo

## 🧹 Preparación de los datos

1. **Clasificación de variables**
   - **Categóricas:** Género, Partner, Dependents, PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, Contract, PaperlessBilling, PaymentMethod.
   - **Numéricas:** SeniorCitizen, Charges.Total, Charges.Monthly, Cuentas_Diarias, GastoTotalAprox (reconstruido).

2. **Preprocesamiento**
   - Eliminación de columnas irrelevantes como IDs y diccionarios originales.
   - Codificación de variables categóricas mediante **One-Hot Encoding**.
   - Creación de la columna `Churn_Yes` a partir de la variable original `Churn`.
   - Reconstrucción aproximada de la variable de gasto total (`GastoTotalAprox`) considerando servicios activos.

3. **Separación de datos**
   - División en conjuntos de **entrenamiento y prueba** (80/20) para evaluación de modelos.

---

## ⚙️ Modelización y justificación de decisiones

Se entrenaron dos modelos distintos para predecir churn:

1. **Regresión Logística**
   - Requiere normalización de las variables para un cálculo correcto de coeficientes.
   - Permite interpretar la contribución de cada variable a la probabilidad de churn.

2. **Random Forest**
   - No requiere normalización.
   - Proporciona importancia de variables basada en reducción de impureza de los árboles.
   
**Justificación:**  
Se eligieron modelos que combinan interpretabilidad (Regresión Logística) y robustez ante correlaciones y escalas (Random Forest). Esto permite comparar desempeño y obtener insights prácticos sobre los factores que influyen en la cancelación.

---

## 📊 Análisis exploratorio (EDA) y gráficos

Durante el análisis exploratorio se realizaron:

- **Matriz de correlación:** para identificar relaciones entre variables numéricas y su correlación con `Churn_Yes`.
- **Boxplots dirigidos:**  
  - `GastoTotalAprox` vs `Churn_Yes`  
  - Variables de contrato (`Contract_One year`, `Contract_Two year`, etc.) vs `Churn_Yes`
- **Gráficos de importancia de variables** para Random Forest y Regresión Logística.

**Insights obtenidos:**
- Contratos a corto plazo y servicios de internet de fibra óptica aumentan riesgo de churn.
- Soporte técnico, contratos largos y planes familiares reducen la probabilidad de cancelación.
- La identificación de clientes con alto riesgo permite diseñar estrategias de retención focalizadas.

---

## 📈 Resultados de los modelos

| Modelo                | Accuracy | Precision | Recall | F1-score |
|----------------------|---------|-----------|--------|----------|
| Regresión Logística   | 0.79    | 0.608     | 0.515  | 0.558    |
| Random Forest         | 0.761   | 0.542     | 0.446  | 0.489    |

- La Regresión Logística presentó mejor desempeño general y facilidad de interpretación.
- Random Forest mostró robustez ante posibles correlaciones y proporcionó ranking de importancia de variables.
- Ambos modelos identificaron factores clave para la cancelación de clientes.

---

## 🚀 Instrucciones para ejecutar el cuaderno

1. **Instalar bibliotecas requeridas**:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
Cargar los datos tratados:
import pandas as pd
df = pd.read_csv("TelecomX_Data_Limpio_Optimizado.csv")
Ejecutar el cuaderno TelecomX_Churn_Analysis.ipynb paso a paso.
El notebook incluye:

Preprocesamiento de datos

Análisis exploratorio (EDA)

Modelización y evaluación

Gráficos de importancia de variables

Conclusiones finales

📌 Conclusión
El análisis permite a Telecom X:

Mejorar la retención de clientes identificando los de mayor riesgo de churn.

Incentivar contratos a largo plazo y servicios complementarios estratégicos.

Diseñar estrategias personalizadas según perfil del cliente, aumentando la fidelización y reduciendo pérdidas por cancelaciones.
