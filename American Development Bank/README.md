Movilidad urbana y productividad económica

Analista de datos en el American Development Bank.

Tu equipo debe entregar un reporte para entender cómo la movilidad urbana (niveles de congestión, tiempos de viaje, retrasos) se relaciona con la productividad económica (PIB per cápita, desempleo) en las principales ciudades del mundo.

El objetivo del banco es identificar en qué ciudades invertir en infraestructura de transporte para aumentar la productividad y el bienestar de la población.

Para ello, usarás dos fuentes reales de datos:

- `Movilidad urbana`: TomTom Traffic Index incluye 1'004.464 de datos de tráfico en tiempo real con valores con tipos de datos errados, faltantes, sentinels, outliers y problemas de calidad, nombres de columnas sin estadarizar y ausencia de columnas creadas a partir de otras.

- `Economía urbana`: OECD Cities incluye  de datos de PIB per cápita, desempleo y población con valores con tipos de datos errados, faltantes, sentinels, outliers y problemas de calidad para los años 2023 y 2024, nombres de columnas sin estadarizar y separadores incorrectos.

Tu misión será limpiar, unir y analizar ambas bases para obtener información útil para la toma de decisiones.


## 📂 Contenido del repositorio
- `S5 American Development Bank mobility_economy.ipynb` → Notebook principal con limpieza, EDA, distribuciones, outliers, visualizaciones y conclusiones.
- `Movilidad urbana y productividad económica.pdf` → Requerimientos y solicitudes del proyecto
[![](https://img.shields.io/badge/📄_Open_specification_PDF-blue?style=for-the-badge)](https://github.com/JFFBMA/Data-Analysis/blob/main/American%20Development%20Bank/Movilidad%20urbana%20y%20productividad%20econ%C3%B3mica.pdf)

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:
[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JFFBMA/Data-Analysis/blob/main/American%20Development%20Bank/S5%20American%20Development%20Bank%20mobility_economy.ipynb)

## 🧠 Objetivo del análisis

1.	Crear un dataset único y limpio a partir de dos fuentes diferentes.
2.	Aplicar limpieza, estandarización y validación de tipos de datos.
3.	Filtrar y enfocar el análisis en el año 2024.
4.	Calcular indicadores agregados (por ciudad–año).
5.	Realizar análisis exploratorios y visuales.
6.	Documentar todos los pasos en Jupyter Notebook, exportar un dataset final y listo para análisis.

