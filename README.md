# Análisis de Tasa de Evasión de Clientes

## 📌 Descripción del Proyecto
Este proyecto implementa un **proceso ETL (Extract, Transform, Load)** y un análisis exploratorio de datos (EDA) sobre la **tasa de evasión de clientes**, con visualizaciones limpias y categorizaciones optimizadas.  
Se detectaron inconsistencias en los valores originales (`Yes` / `No` / variantes y vacíos), las cuales fueron normalizadas para asegurar métricas confiables.

El análisis final incluye:
- Limpieza y estandarización de datos.
- Transformación de categorías inconsistentes.
- Visualización clara de la tasa de evasión.
- Hallazgos clave y recomendaciones de negocio.

---

## 🛠 Herramientas Utilizadas
- **Python 3.x**
- **Pandas** → Limpieza, transformación y manipulación de datos.
- **Matplotlib** → Visualizaciones de la tasa de evasión.
- **Jupyter Notebook** → Documentación del flujo ETL y análisis.



---

## 🔍 Proceso ETL
### 1. **Extracción**
- Fuente: Dataset proporcionado con columna `Evasion`.
- Formato: `.csv` (o equivalente cargado en DataFrame).


### 2. **Transformación**
- **Normalización de valores**:
  - `Yes`, `Y`, `Si`, `Sí`, `1`, `True` → `Sí Evade`
  - `No`, `N`, `0`, `False` → `No Evade`
  - Valores vacíos o desconocidos → `Desconocido`
- Eliminación de espacios y estandarización a minúsculas antes de mapear.
- Cálculo automático del porcentaje de desconocidos.
- Lógica adaptativa.

### 3. **Carga**
- Datos transformados listos para análisis y visualización.
- Visualización final tipo **torta** con colores asignados.

---

## 📊 Hallazgos Clave
1. **Valores inconsistentes**  
   Se identificaron múltiples variantes para `Sí` y `No`, así como entradas vacías y textos irrelevantes, que inflaban artificialmente una tercera categoría.
   
2. **Proporción de evasión real**  
   Tras la limpieza, la proporción `Sí Evade` vs. `No Evade` fue más precisa y redujo sesgos generados por datos mal etiquetados.
   
3. **Impacto de datos faltantes**  
   En este dataset justifica estrategias de mejora de captura de datos.

---

## 💡 Insights y Datos Importantes
- La limpieza de categorías es **crítica** antes de calcular métricas clave como tasas de evasión.
- Los valores faltantes o inconsistentes no son neutros: pueden generar decisiones erróneas si no se gestionan explícitamente.
- La visualización debe ser **intuitiva** y evitar ambigüedades cromáticas.

---


## 📈 Conclusiones
- El dataset presentaba **problemas de calidad de datos** que distorsionaban el análisis.
- Con una estrategia simple de mapeo y limpieza, se obtuvo un indicador de evasión mucho más confiable.
- La detección temprana de valores atípicos o desconocidos permite actuar antes de que estos influyan en modelos predictivos o KPIs.
- El enfoque **ETL + EDA** fue suficiente para entregar un resultado profesional y utilizable para stakeholders.

### Factores Clave Identificados:

1.  **Tipo de Contrato:** Es el factor más influyente. Los clientes con contratos **mes a mes** tienen una tasa de evasión drásticamente más alta que aquellos con contratos anuales o de dos años. Los contratos a largo plazo son un factor clave de retención.

2.  **Antigüedad (Tenure):** La evasión es significativamente más alta entre los **clientes nuevos**. La mayoría de las cancelaciones ocurren en los primeros meses de servicio. A medida que aumenta la antigüedad, la probabilidad de evasión disminuye considerablemente.

3.  **Servicios de Protección y Soporte:** Los clientes que **NO tienen servicios** como `OnlineSecurity`, `OnlineBackup` y, especialmente, `TechSupport` (Soporte Técnico), tienden a cancelar mucho más. Estos servicios parecen aumentar el valor percibido y la dependencia de la plataforma.

4.  **Método de Pago:** Los clientes que utilizan el **cheque electrónico (`Electronic check`)** como método de pago muestran una tasa de evasión notablemente superior a los que usan tarjetas de crédito o débito automático. Esto podría indicar una menor vinculación o problemas en el proceso de pago.


## 🚀 Recomendaciones

-   **Fomentar Contratos a Largo Plazo:** Ofrecer incentivos y descuentos agresivos para que los nuevos clientes opten por contratos anuales en lugar de mes a mes.
-   **Crear un Plan de Fidelización para Nuevos Clientes:** Implementar una campaña de seguimiento y beneficios durante los primeros 6 meses de servicio para superar el período de mayor riesgo de evasión.
-   **Promocionar Servicios de Valor Agregado:** Ofrecer paquetes o descuentos en servicios como `OnlineSecurity` y `TechSupport` al momento de la contratación, especialmente para clientes con contratos mensuales.
-   **Optimizar Métodos de Pago:** Incentivar el uso de métodos de pago automáticos (tarjeta de crédito, débito bancario) y analizar por qué los clientes que pagan con cheque electrónico tienen tantos problemas.

