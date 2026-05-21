# Análisis Estratégico e Histórico de la Evolución del COVID-19 en EE.UU.

Este repositorio contiene los artefactos técnicos, metodológicos y analíticos del proyecto final de Análisis Exploratorio de Datos (EDA) y Modelado Predictivo centrado en el impacto logístico y sanitario del COVID-19 en los Estados Unidos. El proyecto transforma millones de registros crudos en una narrativa de datos orientada a la toma de decisiones estratégicas.

## 📋 Estructura del Proyecto

El proyecto está compuesto por los siguientes documentos principales:

1. **`Proyecto_EDA_Exploratory_Data_Analysis_Grupo_6.ipynb`**: Jupyter Notebook estructurado que contiene todo el pipeline de datos en Python: importación, limpieza avanzada, tratamiento de gobernanza de datos, análisis exploratorio visual (EDA) y la implementación de un algoritmo predictivo de regresión lineal.
2. **`Informe_ejecutivo.pdf`**: Documento corporativo formal dirigido a la dirección (Jonnathan Ospina) que destila los hallazgos técnicos en recomendaciones operativas e interpretaciones de negocio.

---

## 👥 Autores y Contexto
* **Creado por:** Jose Carlos de Santiago Sánchez y Alejandra Duque García.
* **Entorno:** Bootcamp Data Analyst - Proyecto Grupo 6.
* **Tecnologías Clave:** Python (Pandas, NumPy, Scikit-Learn), Plotly Express, Graph Objects, Matplotlib y Seaborn.

---

## 🎯 Objetivos de la Investigación

* **Optimización de Infraestructura:** Identificar dependencias críticas en recursos sanitarios y proponer métricas robustas de capacidad de respuesta.
* **Evaluación de Diagnóstico:** Analizar la efectividad de las campañas masivas de testeo y su correlación con la positividad real.
* **Modelado de Tendencias:** Construir un modelo analítico capaz de proyectar la mortalidad a corto plazo en base a la carga hospitalaria actual para actuar de forma proactiva.

---

## 📈 Hallazgos y Conclusiones Clave

A través del análisis detallado en el Notebook y consolidado en el informe, se alcanzaron las siguientes conclusiones críticas:

1. **Gobernanza y Saneamiento de Datos:** Se identificó un severo desorden administrativo e inconsistencia en los reportes hospitalarios durante los primeros meses. Para mitigar este ruido temporal, el análisis principal se acotó a partir del **1 de mayo de 2020**, neutralizando valores nulos e incrementos acumulados negativos mediante técnicas avanzadas de imputación y acotación.
2. **Picos de Presión Crítica:** Se detectó el punto de máxima tensión en el sistema sanitario estadounidense entre **diciembre de 2020 y febrero de 2021**, coincidiendo directamente con los periodos festivos de fin de año.
3. **Interdependencia de Recursos UCI:** Se observó una correlación lineal extremadamente fuerte entre la ocupación de camas UCI y la necesidad inmediata de ventiladores mecánicos, evidenciando que ambos elementos actúan como un cuello de botella único.
4. **Comportamiento Asintótico del Sistema:** Al evaluar la estrategia de testeo masivo, se demostró que a pesar del incremento en la capacidad de pruebas, la positividad se mantuvo alta. Del mismo modo, en escenarios de colapso sanitario masivo, la relación de predicción lineal sufre una ruptura (comportamiento asintótico), disparando la mortalidad real de forma exponencial por falta de atención oportuna.
5. **Capacidad Predictiva del Modelo:** Se entrenó un modelo de regresión lineal enfocado en estimar fallecimientos basándose en los casos positivos y las hospitalizaciones del momento. El modelo demostró una alta precisión relativa con un coeficiente de determinación **$R^2 = 0.77$** y un **RMSE = 536.72**, subrayando que la carga de internamientos actual es el predictor más fuerte de la mortalidad a corto plazo (ventana de 3 semanas).

---

## 🚀 Recomendaciones Estratégicas Formuladas

* **Redefinición de Métricas (Unidad Operativa Completa):** Los hospitales no deben medir su capacidad en función de camas vacías individuales. Se recomienda monitorear "bloques logísticos concurrentes" compuestos de manera estricta por: **Cama + Ventilador + Personal Especializado**.
* **Activación Proactiva de Suministros:** Transformar el modelo predictivo en un *Tablero de Alerta Temprana*. Un incremento sostenido en las hospitalizaciones hoy debe gatillar automáticamente el abastecimiento logístico para las próximas tres semanas antes de alcanzar el pico de fallecimientos.
* **Modelado Dinámico:** Integrar de forma urgente variables cualitativas complementarias (como nuevas cepas o campañas de vacunación masiva) para mantener la calibración del algoritmo en el largo plazo.

---

## 🛠️ Instrucciones de Uso (Notebook)

Para reproducir el análisis o auditar el código:
1. Asegúrate de tener instalado Python 3 y un entorno de Jupyter (o Google Colab).
2. Coloca el archivo fuente de datos `national-history.csv` en el mismo directorio que el notebook.
3. Ejecuta las celdas en orden correlativo para observar el proceso de carga de librerías (`pandas`, `numpy`, `plotly`, `seaborn`), limpieza de anomalías y el posterior entrenamiento del modelo `Scikit-Learn`.

---

## 📂 Estructura del Proyecto

A continuación se detalla la organización real de los archivos y directorios dentro del espacio de trabajo:

```text
PROYECTO_EDA/
├── data/
│   ├── Informe_ejecutivo.pdf    # Resumen hallazgos y novedades
│   └── national-history.csv     # Ignorado por el .gitignore
├── notebook/
│   └── Proyecto_EDA_Exploratory_Data_Analysis_Grupo_6.ipynb     # Jupyter notebook con codigo y gráficos
├── .gitignore
├── LICENSE
└── README.md
