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
Paso-Acción-Resultado para el negocio
1. Cargar y explorar-Cargar y explorar plans, users_latam, usage.-Visión clara de la estructura y tipos de columna de cada dataset.
2. Identificación de problemas de calidad-Contar nulos, detectar sentinels, revisar fechas fuera de rango.-Lista priorizada de  que pueden sesgar decisiones.
3. Limpieza básica-Reemplazar sentinels, convertir fechas, imputar o marcar NA según reglas.-Datos consistentes y listos para análisis estadístico.
4. Summary statistics-Revisar las medidas clave en variables categóricas y numéricas.-Medidas clave (media, mediana, percentiles) que muestran el comportamiento típico y extremo
5. Visualización & outliers-Creación de histogramas y boxplots.-Visualización de sesgos, patrones de usuarios o datos atípicos.
6. Segmentación-Crear segmentaciones basadas en reglas claras; visualizar proporciones con countplots.-Segmentos accionables que permiten diseñar ofertas, campañas y migraciones de plan.
7. Insight ejecutivo-Redactar conclusiones y recomendaciones comerciales basadas en los pasos anteriores.-Responder a las preguntas del negocio y proponer acciones concretas.
8. Publicación-Subir tu notebook + README a GitHub.-Entrega reproducible para revisión y ejecución por stakeholders.

## 📂 Contenido del repositorio
- `ConnectaTel.ipynb` → Notebook principal con limpieza, EDA, distribuciones, outliers, visualizaciones y conclusiones.
  

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:
[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://drive.google.com/file/d/1SpZEzdGgMO5SclBzOJwkqdBwhHoT37hZ/view?usp=drive_link)

## 🧠 Objetivo del análisis

1.	Crear un dataset único y limpio a partir de dos fuentes diferentes.
2.	Aplicar limpieza, estandarización y validación de tipos de datos.
3.	Filtrar y enfocar el análisis en el año 2024.
4.	Calcular indicadores agregados (por ciudad–año).
5.	Realizar análisis exploratorios y visuales.
6.	Documentar todos los pasos en Jupyter Notebook, exportar un dataset final y listo para análisis.


