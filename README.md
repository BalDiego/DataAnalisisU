# DataAnalisisU
# Proyecto de Analítica de Datos – Netflix

## Descripción del Proyecto
El proyecto toma como referencia el funcionamiento de la plataforma de streaming Netflix
, la cual genera grandes volúmenes de datos provenientes de interacciones de usuarios, reproducciones, búsquedas y sistemas de recomendación.

El objetivo es diseñar una arquitectura analítica basada en un Data Warehouse que permita centralizar y analizar información relacionada con el comportamiento de los usuarios, el consumo de contenido y los niveles de retención dentro de la plataforma.

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


## Objetivos Analíticos

- Analizar patrones de consumo  
- Identificar factores de retención y abandono  
- Medir el engagement de usuarios  
- Evaluar la efectividad de recomendaciones  
- Desarrollar modelos predictivos de churn

---

## Variables Analíticas del Proyecto

Las variables del proyecto se clasifican en:

- Variables independientes: tiempo de visualización, frecuencia de uso, inactividad, diversidad de contenido, tipo de suscripción, interacción con recomendaciones.
- Variables dependientes: retención, engagement y churn (probabilidad de abandono).
- Métricas de evaluación: CTR, tasa de conversión, rating promedio, porcentaje de usuarios activos.
``
### Tiempo de Visualización
- Tipo: Cuantitativa continua  
- Unidad: Minutos / horas consumidas  
- Relación: ↑ tiempo de visualización → ↑ retención  

### Frecuencia de Uso
- Tipo: Cuantitativa discreta  
- Unidad: Número de sesiones por semana  
- Relación: ↑ frecuencia → ↓ churn  

### Tiempo de Inactividad
- Tipo: Cuantitativa continua  
- Unidad: Días sin actividad  
- Relación: ↑ inactividad → ↑ probabilidad de abandono  

### Diversidad de Contenido Consumido
- Tipo: Cuantitativa discreta  
- Unidad: Cantidad de géneros consumidos  
- Relación: ↑ diversidad → ↑ retención  

### Engagement
- Tipo: Cuantitativa continua  
- Unidad: Score o índice compuesto  
- Relación: ↑ engagement → ↑ retención  

### Retención
- Tipo: Cuantitativa continua  
- Unidad: Porcentaje de usuarios activos  
- Relación: Variable dependiente principal  

### Churn (Abandono)
- Tipo: Binaria  
- Unidad: 0 = activo / 1 = cancelado  
- Relación: Variable objetivo del análisis predictivo  

### Rating Promedio
- Tipo: Cuantitativa continua derivada de una escala ordinal  
- Unidad: Promedio de calificaciones en escala de 1 a 5  
- Relación: A mayor rating promedio, mayor satisfacción y posible retención.

### Interacción con Recomendaciones
- Tipo: Cuantitativa continua  
- Unidad: CTR / porcentaje de conversión  
- Relación: ↑ interacción → ↑ engagement  

### Búsquedas Realizadas
- Tipo: Cuantitativa discreta  
- Unidad: Número de búsquedas  
- Relación: Altas búsquedas sin reproducción → posible frustración  



---


## Hipótesis de Análisis

El proyecto se basa en las siguientes hipótesis:

| Variable que se está midiendo | Indicador de análisis | Prueba de Fiabilidad / Método de Validación |
|---|---|---|
| Tiempo de visualización y frecuencia de uso | Los usuarios que presentan mayor tiempo de visualización y utilizan la plataforma con mayor frecuencia tienen una mayor probabilidad de retención, debido a que muestran un nivel más alto de compromiso con el servicio de streaming. | Correlación de Pearson/Spearman y regresión logística para evaluar su influencia sobre la retención. | 
| Diversidad de contenido consumido | Los usuarios que consumen una mayor variedad de géneros, categorías o formatos de contenido presentan menor probabilidad de churn, debido a que encuentran más opciones relevantes dentro del catálogo de la plataforma. | Análisis de correlación y segmentación de usuarios mediante clustering. | 
| Recomendaciones personalizadas | Las recomendaciones personalizadas incrementan la probabilidad de reproducción de contenido y aumentan el engagement del usuario, al facilitar el descubrimiento de títulos acordes con sus preferencias e historial de consumo. | Análisis de CTR (Click Through Rate), tasa de conversión y regresión estadística. |
| Fuente de descubrimiento del contenido | Las películas o series reproducidas a partir de recomendaciones personalizadas tienen mayor probabilidad de ser vistas que aquellas encontradas únicamente mediante búsqueda manual, debido a la influencia del sistema de recomendación en el comportamiento del usuario. | Comparación de tasas de reproducción según fuente de descubrimiento y prueba Chi-cuadrado. | 


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
