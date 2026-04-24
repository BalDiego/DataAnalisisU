# DataAnalisisU
# Proyecto de Analítica de Datos – Plataforma de Streaming

## Descripción del Proyecto
Este proyecto consiste en el diseño e implementación de una solución de analítica de datos para una plataforma de streaming. Se construye un **Data Warehouse** a partir de un sistema transaccional (OLTP) con el objetivo de analizar el comportamiento de los usuarios y generar insights que apoyen la toma de decisiones.

El sistema integra datos de:
- Usuarios  
- Reproducciones  
- Búsquedas  
- Calificaciones  
- Suscripciones  

---

## Planteamiento del Problema
La plataforma genera grandes volúmenes de datos, pero carece de una estructura analítica que permita su explotación eficiente. Esto dificulta responder preguntas clave como:

- ¿Qué factores influyen en la retención de usuarios?  
- ¿Qué patrones indican riesgo de abandono (churn)?  
- ¿Qué tan efectivas son las recomendaciones?  

Se propone el desarrollo de un **Data Warehouse** y la aplicación de técnicas analíticas para transformar datos en información estratégica.

---

## Arquitectura de la Solución

### Sistema Transaccional (OLTP)
Modelo normalizado que captura:
- Actividad de usuarios  
- Historial de consumo  
- Interacciones (ratings, búsquedas)  
- Estado de suscripciones  

### Data Warehouse (OLAP)
Modelo dimensional tipo **esquema estrella**, compuesto por:

** Tablas de hechos:**
- Fact_Consumo  
- Fact_Ratings  
- Fact_Busquedas  
- Fact_Suscripciones  
- Fact_Recomendaciones  

** Dimensiones:**
- Dim_Usuario  
- Dim_Contenido  
- Dim_Tiempo  
- Dim_Dispositivo  

---

## Proceso ETL
Se implementa un flujo ETL que:

1. Extrae datos desde el sistema OLTP  
2. Transforma y limpia la información  
3. Carga los datos en el Data Warehouse  

---

## Hipótesis de Análisis

El proyecto se basa en las siguientes hipótesis:

- El **tiempo de visualización** impacta positivamente en la retención  
- La **frecuencia de uso** reduce el churn  
- La **inactividad** incrementa el riesgo de abandono  
- La **diversidad de contenido** reduce la probabilidad de churn  
- Las **recomendaciones personalizadas** aumentan el engagement  
- La **satisfacción del usuario** (ratings) se asocia con mayor retención  

---

## Objetivos Analíticos

- Analizar patrones de consumo  
- Identificar factores de retención y abandono  
- Medir el engagement de usuarios  
- Evaluar la efectividad de recomendaciones  
- Desarrollar modelos predictivos de churn  

---

## Aplicaciones Analíticas

El Data Warehouse permite:

- Creación de dashboards (BI)  
- Análisis exploratorio de datos (EDA)  
- Modelos de Machine Learning  
  - Predicción de churn  
  - Segmentación de usuarios  

---

## Resultados Esperados

- Identificación de variables clave de retención  
- Mejora en la personalización del contenido  
- Soporte a la toma de decisiones basada en datos  
- Optimización de la experiencia del usuario  

---


## Conclusión

Este proyecto demuestra cómo la implementación de un Data Warehouse y técnicas de análisis de datos permite transformar datos operativos en conocimiento estratégico, facilitando la optimización de la retención y el engagement en plataformas digitales.
