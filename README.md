# 📊 Proyecto-EDA-Grupo-6.

Este proyecto realiza un **Análisis Exploratorio de Datos (EDA)** detallado sobre la evolución histórica de la pandemia del COVID-19 a nivel nacional en Estados Unidos. El objetivo principal es evaluar la calidad de los datos epidemiológicos, identificar patrones de distribución, analizar las tendencias temporales y entender la presión ejercida sobre la infraestructura hospitalaria (camas generales, UCI y ventiladores).

---

## 🛠️ Fases del Proyecto

### 1. Preparación y Calidad de Datos
* **Carga y Estructura:** Procesamiento del dataset `national-history.csv`, el cual contiene **420 entradas y 17 columnas** con métricas clave de contagios, pruebas y estado del sistema de salud.
* **Limpieza de Datos:** * Tratamiento de valores nulos (`NaN`) significativos en variables acumuladas e instantáneas.
  * Uso de propagación hacia adelante (`ffill`) y relleno con ceros (`0`) para métricas de estado actual (`hospitalizedCurrently`).
  * Imputación por media aritmética para variables acumuladas complejas y resultados negativos.
* **Consistencia y Reducción:** Conversión de la columna `date` a formato `datetime`, ordenamiento cronológico del histórico y eliminación de la columna estática `states` al tratarse de un análisis consolidado federal.

### 2. Análisis de Distribución y Outliers
* Monitoreo de asimetrías mediante diagramas de caja (*Box plots*) para las variables `deathIncrease`, `totalTestResultsIncrease` y `positiveIncrease`.
* **Detección de Anomalías:** Implementación del método de Rango Intercuartílico (IQR), aislando **28 outliers** específicos en el incremento de muertes (`deathIncrease`), identificando estadísticamente los días con picos críticos de mortalidad.

### 3. Tendencias Temporales y Carga Sanitaria
* **Casos vs. Muertes:** Análisis de desfase temporal (*lag*) entre la curva de `positiveIncrease` y `deathIncrease`, visualizando cómo los picos de contagios precedían consistentemente a las olas de mortalidad debido al periodo biológico de incubación.
* **Presión Hospitalaria:** Mapeo de la evolución e interdependencia de pacientes en camas generales (`hospitalizedCurrently`), cuidados intensivos (`inIcuCurrently`) y asistencia respiratoria mecánica (`onVentilatorCurrently`).

### 4. Relaciones entre Variables y Correlación
* **Matriz de Pearson:** Cálculo de coeficientes de correlación lineal para cuantificar el impacto directo de la propagación del virus sobre la ocupación logística del sector salud.
* **Visualización Avanzada:** Construcción de gráficos de dispersión (*Scatter plots*) multivariables cruzando el volumen de hospitalizados frente a UCI, segmentado de forma cromática por el uso de ventiladores activos.
* **Visualización de la Carga:** El scatter plot de `hospitalizedCurrently` vs `inIcuCurrently`, coloreado por `onVentilatorCurrently`.
* **Interactividad con Plotly Express:** Se desarrollaron gráficos dinámicos que permiten explorar las series temporales y distribuciones de manera interactiva, facilitando el filtrado visual de datos, el aislamiento de variables específicas y la lectura de valores exactos mediante *tooltips* al pasar el cursor.

---

## 📈 Tecnologías Utilizadas

* **Python 3.x**
* **Pandas** & **NumPy** — Manipulación, limpieza y estructuración de datos.
* **Plotly Express** — Creación de gráficos interactivos y dinámicos para la exploración de datos en tiempo real.
* **Matplotlib** & **Seaborn** — Visualización estática avanzada y matrices de correlación.
* **Scipy (stats)** — Análisis de distribuciones, cálculo de IQR, asimetría y curtosis.
---

## 📁 Estructura del Repositorio

```text
├── data/
│   └── national-history.csv       # Dataset original con el histórico de métricas
├── notebooks/
│   └── Proyecto_EDA_Exploratory_Data_Analysis_Grupo_6.ipynb # Notebook de Jupyter con el desarrollo del código
└── README.md               # Dependencias del entorno
