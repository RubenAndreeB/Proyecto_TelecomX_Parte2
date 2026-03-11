# 🚀 Predicción de Churn en Telecomunicaciones | Machine Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C4C4C?style=flat&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completado-success.svg)

## 📌 Descripción del Proyecto
Este proyecto de Ciencia de Datos tiene como objetivo **predecir el abandono de clientes (Churn)** en una empresa de telecomunicaciones. A través de un Análisis Exploratorio de Datos (EDA) profundo, selección de características estadísticamente significativas y el entrenamiento de múltiples modelos de Machine Learning, identificamos no solo *quién* es propenso a cancelar el servicio, sino *por qué*.

Más allá del código, este proyecto se traduce en **estrategias de retención accionables** para el equipo de negocio.

---

## 🛠️ Tecnologías y Herramientas
* **Lenguaje:** Python
* **Manipulación de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Logistic Regression, Random Forest, SVM, KNN, Gradient Boosting)
* **Estadística:** Pruebas de Chi-Cuadrado ($\chi^2$), Correlación de Pearson

---

## 🔬 Metodología

### 1. Preprocesamiento y Limpieza
* **Selección de Características:** Se aplicó la prueba estadística de Chi-Cuadrado para variables categóricas. Se demostró empíricamente que variables como `Gender` (Género) y `PhoneService` no aportaban valor predictivo, siendo eliminadas para optimizar el modelo.
* **Transformación:** Aplicación de *One-Hot Encoding* para variables categóricas (`drop_first=True` para evitar multicolinealidad) y `StandardScaler` para las variables numéricas continuas.
* **División de Datos:** *Train/Test Split* (80/20) estratificado para mantener la proporción de la clase minoritaria (Churn).

### 2. Modelado Predictivo
Se entrenaron y evaluaron diversos algoritmos para encontrar el equilibrio perfecto entre explicabilidad y precisión:
1. **Regresión Logística (Normal y Balanceada):** Excelente para entender la dirección del impacto (coeficientes) de cada variable.
2. **Random Forest & Gradient Boosting:** Algoritmos de ensamble robustos para capturar relaciones no lineales complejas.
3. **Support Vector Machines (SVM) & KNN:** Modelos de frontera y distancia para segmentación de perfiles.

---

## 📊 Principales Hallazgos (Business Insights)

El consenso entre los diferentes algoritmos nos permitió confirmar qué factores son los verdaderos impulsores del abandono:

1. **La trampa del "Mes a Mes":** El contrato mensual (`Contract_Month-to-month`) es el predictor de fuga más fuerte. La falta de compromiso a largo plazo deja al cliente vulnerable.
2. **El riesgo en los primeros meses (Tenure):** El riesgo de abandono es crítico al inicio y decae exponencialmente conforme el usuario supera la etapa de madurez en la plataforma.
3. **Sensibilidad al Precio:** Cargos totales y mensuales elevados incrementan consistentemente la probabilidad de Churn.
4. **La Paradoja de la Fibra Óptica:** Los clientes con Fibra Óptica muestran una mayor propensión al abandono frente a los de DSL, sugiriendo una posible desconexión entre el costo premium y la estabilidad del servicio.

---

## 💡 Estrategias de Retención Propuestas

Basados en los modelos predictivos, proponemos las siguientes acciones clave para el área de Negocio/Marketing:

| Estrategia | Acción Recomendada | Justificación Técnica |
| :--- | :--- | :--- |
| **Conversión Contractual** | Campañas de *upselling* con beneficios exclusivos para incentivar la migración de usuarios "Mes a Mes" a planes anuales. | El tipo de contrato posee el coeficiente de mayor impacto predictivo hacia el abandono en los modelos lineales. |
| **Programa "Primeros Pasos"** | Monitoreo proactivo, encuestas de satisfacción y soporte prioritario durante los primeros 6 meses. | La variable `Tenure` demuestra que la fuga se concentra masivamente en las etapas tempranas. |
| **Optimización de Valor** | Ajustes de tarifas personalizados para clientes con estrés financiero (cargos altos y baja antigüedad). | Variables de costo son predictores primarios en Random Forest y KNN. |

---

## 💻 Cómo ejecutar el proyecto localmente

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/TuUsuario/Telecom_Churn_Prediction.git](https://github.com/TuUsuario/Telecom_Churn_Prediction.git)
Instala las dependencias necesarias:

Bash
pip install -r requirements.txt
Abre el Jupyter Notebook:

Bash
jupyter notebook Proyecto_TelecomX_Parte2.ipynb
