# 🐟 TFM: Predicción y Análisis de Datos de Lonjas de Galicia con Microsoft Fabric

Este proyecto desarrolla una solución *End-to-End* de ingeniería de datos y analítica avanzada para capturar, transformar y analizar el volumen y precios de venta en las lonjas gallegas, integrando factores oceanográficos.

La arquitectura está construida sobre **Microsoft Fabric** siguiendo una arquitectura **Medallion (Bronze, Silver, Gold)**.

---

## 🏗️ Arquitectura del Proyecto

El flujo de trabajo sigue el ciclo de vida del dato desde su ingesta hasta su explotación analítica:

```text
[ Fuentes XML / CSV ] 
         │
         ▼
 🟤 BRONZE (Ingesta Raw / Lakehouse)
         │
         ▼ (Limpieza y Tipado PySpark)
 ⚪ SILVER (Tablas Delta Limpias)
         │
         ▼ (Agregaciones y Modelado Estrella)
 🟡 GOLD (Modelos de Análisis / Tablas Finales)
         │
         ▼
 📊 Power BI (Modelo Semántico e Informe)