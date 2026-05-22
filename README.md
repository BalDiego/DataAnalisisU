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
- Tipo: Cuantitativa ordinal  
- Unidad: Escala de 1–5  
- Relación: ↑ satisfacción → ↑ retención  

### Interacción con Recomendaciones
- Tipo: Cuantitativa continua  
- Unidad: CTR / porcentaje de conversión  
- Relación: ↑ interacción → ↑ engagement  

### Búsquedas Realizadas
- Tipo: Cuantitativa discreta  
- Unidad: Número de búsquedas  
- Relación: Altas búsquedas sin reproducción → posible frustración  

### Tipo de Suscripción
- Tipo: Categórica nominal  
- Unidad: Free / Premium  
- Relación: Premium → mayor engagement y retención  


---


## Hipótesis de Análisis

El proyecto se basa en las siguientes hipótesis:

- El **tiempo de visualización** impacta positivamente en la retención  
- La **frecuencia de uso** reduce el churn  
- La **inactividad** incrementa el riesgo de abandono  
- La **diversidad de contenido** reduce la probabilidad de churn  
- Las **recomendaciones personalizadas** aumentan el engagement  
- La **satisfacción del usuario** (ratings) se asocia con mayor retención
- Los usuarios con **suscripción premium** presentan mayores niveles de engagement y retención que los usuarios gratuitos.
- Un alto número de **búsquedas** sin reproducción posterior puede indicar baja satisfacción del usuario.
 

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
