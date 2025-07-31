# Análisis y Predicción de Cancelación de Clientes

Este cuaderno presenta un análisis del conjunto de datos de clientes de una empresa de telecomunicaciones con el objetivo de identificar los factores clave que influyen en la cancelación del servicio (Churn) y desarrollar modelos predictivos para predecir qué clientes son más propensos a irse.

## Contenido del Cuaderno

1.  **Preparación de los Datos:**
    *   Carga del conjunto de datos desde una URL.
    *   Expansión de columnas anidadas (cliente, teléfono, internet, cuenta).
    *   Conversión de columnas de cargos a formato numérico.
    *   Guardado del DataFrame limpio en un archivo CSV.
    *   Eliminación de columnas irrelevantes (`customerID`).

2.  **Análisis y Balanceo de Datos:**
    *   Cálculo de la proporción de clientes que cancelan (Churn).
    *   Eliminación de filas con valores vacíos en la variable objetivo (`Churn`).
    *   Aplicación de SMOTE (Synthetic Minority Over-sampling Technique) para balancear las clases de la variable objetivo, abordando el desbalance existente.

3.  **Correlación y Selección de Variables:**
    *   Escalado de las características utilizando `StandardScaler`.
    *   Cálculo y visualización de la matriz de correlación para entender las relaciones entre las variables y con la variable objetivo (`Churn`).
    *   Selección de variables con una correlación absoluta superior a un umbral definido (`0.2`) con la variable objetivo.

4.  **Modelado Predictivo:**
    *   División del conjunto de datos en conjuntos de entrenamiento y prueba.
    *   Entrenamiento de tres modelos de clasificación:
        *   Regresión Logística
        *   Árbol de Decisión
        *   Random Forest
    *   Evaluación de cada modelo utilizando métricas clave (Exactitud, Precisión, Recall, F1-score) y visualización de las matrices de confusión.

5.  **Interpretación y Conclusiones:**
    *   Análisis comparativo del rendimiento de los modelos.
    *   Identificación de las variables más importantes para la predicción de Churn según cada modelo.
    *   Interpretación de los factores clave que influyen en la cancelación de clientes (cargos, antigüedad, método de pago, tipo de servicio, etc.).
    *   Propuesta de estrategias de retención basadas en los hallazgos del análisis.

## Resultados Clave

*   El conjunto de datos original presentaba un desbalance significativo en la variable Churn, lo cual fue abordado con SMOTE.
*   El modelo de **Random Forest** demostró ser el más efectivo para predecir la cancelación de clientes basado en las métricas evaluadas en el conjunto de prueba.
*   Las variables más influyentes en la cancelación incluyen los **cargos totales y mensuales**, la **antigüedad del cliente**, el **método de pago (cheque electrónico)**, el **tipo de servicio de internet (fibra óptica)**, la **facturación electrónica** y el **tipo de contrato (contrato a dos años como factor de no cancelación)**.

## Estrategias de Retención Sugeridas

Las estrategias de retención deben enfocarse en los clientes identificados como de alto riesgo, prestando especial atención a aquellos con altos cargos, baja antigüedad, que utilizan cheque electrónico, tienen servicio de fibra óptica o facturación electrónica. Promover contratos a largo plazo es también una estrategia clave para la retención.

## Uso

Para ejecutar este cuaderno, asegúrate de tener las bibliotecas de Python necesarias instaladas (`pandas`, `numpy`, `sklearn`, `seaborn`, `matplotlib`, `imblearn`). Puedes ejecutar las celdas secuencialmente para replicar el análisis y los resultados.