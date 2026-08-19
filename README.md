# telecom-analysis
El objetivo principal de este análisis es evaluar el comportamiento real de consumo (llamadas, mensajes y uso de datos) de los clientes de la empresa de telecomunicaciones **ConnectaTel** en Latinoamérica. 
A través de este estudio estadístico y exploratorio se busca:
- Identificar patrones de consumo según la edad y el tipo de plan contratado.
- Detectar datos atípicos (*outliers*) o inconsistencias de calidad en la base de datos.
- Segmentar a los usuarios para diseñar mejores ofertas comerciales, optimizar la retención de clientes (*churn*) y promover estrategias de *upselling*.

- ## 📊 Datasets Utilizados
El análisis integra información proveniente de tres fuentes de datos principales:

1. **`plans.csv`**: Catálogo de los planes comerciales actuales (`Básico` y `Premium`), especificando cuotas de minutos, SMS, GB incluidos y tarifas por excedentes.
2. **`users_latam.csv`**: Registro demográfico de los clientes (ID, nombre, edad, ciudad, fecha de registro, plan asignado y estado de *churn*).
3. **`usage.csv`**: Registro detallado de la actividad real generada por los usuarios (tipo de evento: llamadas o mensajes, fecha, duración de la llamada y longitud del mensaje).

---
## 🛠️ Etapas del Análisis Realizadas

1. **Carga y Exploración Inicial:**
   - Inspección de la estructura, dimensiones (`.shape`) y tipos de datos (`.info()`) de cada dataset.
2. **Identificación y Limpieza de Calidad de Datos:**
   - Detección e imputación de valores *sentinels* (por ejemplo, `-999` en edad reemplazado por la mediana, y `?` en ciudad convertido a valores nulos).
   - Manejo de fechas inconsistentes o fuera de rango (registros con fechas en 2026 reemplazados por `NaT`).
   - Confirmación de valores nulos con patrón MAR (*Missing At Random*) en variables de consumo (`duration` vs `length`).
3. **Análisis Estadístico Descriptivo:**
   - Cálculo de medidas de tendencia central (media, mediana) y dispersión para evaluar el comportamiento típico y las variaciones.
4. **Visualización y Detección de Outliers:**
   - Uso de histogramas y diagramas de caja (*boxplots*) combinados con el método del Rango Intercuartílico ($IQR$) para identificar consumos extremos o errores de registro.
5. **Segmentación de Clientes:**
   - Clasificación demográfica por grupos de edad (`Joven`, `Adulto`, `Adulto Mayor`).
   - Categorización por intensidad de uso (`Bajo uso`, `Uso medio`, `Alto uso`).
6. **Insights Ejecutivos y Recomendaciones Comercial:**
   - Formulación de propuestas para la estructuración de nuevos planes orientados a perfiles específicos y estrategias para reducir la pérdida de clientes
