# 🌍 Análisis de la Felicidad Mundial con Big Data y Google Cloud

Este proyecto analiza y compara la percepción de felicidad global utilizando dos fuentes:
- **World Happiness Report 2023** (perspectiva socioeconómica)
- **Hedonometer** (perspectiva emocional en tiempo real vía redes sociales)

Se automatiza el proceso de recolección, almacenamiento y visualización de datos mediante herramientas de **Google Cloud Platform (GCP)** y se presenta en un dashboard interactivo con **Looker Studio**.

---

## 🎯 Objetivo

Desarrollar un pipeline completo que recoja datos del Hedonometer, los almacene en la nube y los combine con los del World Happiness Report para generar visualizaciones significativas sobre la felicidad mundial.

## 🛠️ Tecnologías usadas

| Herramienta             | Función |
|-------------------------|---------|
| Google Cloud Storage    | Almacenamiento de datos JSON y CSV |
| Google Cloud Functions  | ETL desde API de Hedonometer |
| Google Cloud Scheduler  | Automatización semanal de recolección |
| Google Dataflow         | Transformación inicial (se descartó) |
| BigQuery                | Análisis de datos |
| Looker Studio           | Dashboard final de visualización |

---

## ⚙️ Arquitectura del Proyecto

```mermaid
flowchart TD
    A[Cloud Scheduler] --> B[Cloud Function]
    B --> C[Google Cloud Storage]
    C --> D[BigQuery]
    D --> E[Looker Studio Dashboard]

---

## 📈 Dashboards

Visualizaciones interactivas de:
- Comparación Hedonometer vs World Happiness Report
- Mapa de felicidad global
- Correlación entre PIB per cápita y felicidad
- Evolución de menciones de felicidad por año

> ⚠️ [Dashboard original](https://lookerstudio.google.com/reporting/5d131ad4-213d-45ee-98ab-b6ad5e688c63)  
---

## 🔁 Flujo de datos

1. **Cloud Function (`main.py`)** recolecta datos de la API Hedonometer.
2. **Scheduler** la activa cada miércoles.
3. Los datos se guardan automáticamente en **Cloud Storage**.
4. Se visualizan desde **BigQuery** usando Looker Studio.


---

## 📄 Referencias

- [World Happiness Report 2023](https://www.kaggle.com/datasets/ajaypalsinghlo/world-happiness-report-2023)
- [Hedonometer API](https://hedonometer.org/)
- [Documentación de Google Cloud](https://cloud.google.com/)

---
