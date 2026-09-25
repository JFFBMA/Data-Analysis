# Uso de Servicios móviles en ConnectaTel

Analista de datos en ConnectaTel.
Tu equipo debe entregar un reporte para entender cómo los clientes usan realmente los servicios móviles (llamadas y mensajes).

## Objetivo
El objetivo de la empresa es identificar patrones de uso, detectar comportamientos atípicos y comprender qué segmentos de clientes muestran necesidades diferenciadas, con el fin de optimizar la oferta comercial y mejorar la experiencia del usuario.

## Fuente de datos
Para ello, trabajarás con tres fuentes de datos:
- plans.csv: los planes actuales (precio, minutos incluidos, GB incluidos, costo por extra).
- users_latam.csv: información de clientes: edad, ciudad, fecha de registro, plan contratado.
- usage.csv: el detalle de uso real: llamadas (duración) y mensajes (longitud).
Explorar, limpiar y analizar estas bases de datos para construir una visión clara, confiable y accionable sobre el comportamiento de uso de los clientes y cómo varía entre diferentes grupos de usuarios.

##🔄 Flujo general del proyecto

Paso	                    Acción	                                      Resultado para el negocio
1. Cargar y explorar	    Cargar y explorar plans, users_latam, usage.	Visión clara de la estructura y tipos de columna de cada dataset.
2. Identificación de 	    Contar nulos, detectar sentinels, revisar fechas fuera de rango.	Lista priorizada de problemas que pueden sesgar decisiones.
   problemas de calidad
4. Limpieza básica	Reemplazar sentinels, convertir fechas, imputar o marcar NA según reglas.	Datos consistentes y listos para análisis estadístico.
5. Summary statistics	Revisar las medidas clave en variables categóricas y numéricas.	Medidas clave (media, mediana, percentiles) que muestran el comportamiento típico y extremo
6. Visualización & outliers	Creación de histogramas y boxplots.	Visualización de sesgos, patrones de usuarios o datos atípicos.
7. Segmentación	Crear segmentaciones basadas en reglas claras; visualizar proporciones con countplots.	Segmentos accionables que permiten diseñar ofertas, campañas y migraciones de plan.
8. Insight ejecutivo	Redactar conclusiones y recomendaciones comerciales basadas en los pasos anteriores.	Responder a las preguntas del negocio y proponer acciones concretas.
9. Publicación	Subir tu notebook + README a GitHub.	Entrega reproducible para revisión y ejecución por stakeholders.

## 📂 Contenido del repositorio
- `ConnectaTel.ipynb` → Notebook principal con limpieza, EDA, distribuciones, outliers, visualizaciones y conclusiones.
- `Movilidad urbana y productividad económica.pdf` → Requerimientos y solicitudes del proyecto
[![](https://img.shields.io/badge/📄_Open_specification_PDF-blue?style=for-the-badge)](./Movilidad%20urbana%20y%20productividad%20econ%C3%B3mica.pdf)

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:
[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://drive.google.com/file/d/1zcLr_8yHakREKQdlSxigJ7wAAmYhhK6q/view?usp=sharing)

## 🧠 Objetivo del análisis

1.	Crear un dataset único y limpio a partir de dos fuentes diferentes.
2.	Aplicar limpieza, estandarización y validación de tipos de datos.
3.	Filtrar y enfocar el análisis en el año 2024.
4.	Calcular indicadores agregados (por ciudad–año).
5.	Realizar análisis exploratorios y visuales.
6.	Documentar todos los pasos en Jupyter Notebook, exportar un dataset final y listo para análisis.


