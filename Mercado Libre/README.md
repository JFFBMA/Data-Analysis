# P4 Análisis de embudo y retención para MercadoLibre

## 📊 Resumen del proyecto

Este proyecto analiza el comportamiento de los usuarios de MercadoLibre a lo largo de dos dimensiones principales:

* **Embudo de conversión:** permite identificar en qué etapas del proceso de compra se producen las mayores pérdidas de usuarios.
* **Retención de usuarios:** permite analizar qué porcentaje de usuarios continúa activo después de 7, 14, 21 y 28 días, tanto por cohorte como por país.

El análisis utiliza información correspondiente al período comprendido entre el **1 de enero de 2025 y el 31 de agosto de 2025**.

---

## 🎯 Objetivo del proyecto

El objetivo es identificar los principales puntos de fricción dentro del proceso de conversión y determinar cómo se comporta la retención de los usuarios a lo largo del tiempo.

En particular, el análisis busca responder:

1. ¿Cuál es la tasa de conversión entre las principales etapas del embudo?
2. ¿En qué etapa se presenta la mayor pérdida porcentual de usuarios?
3. ¿Cómo varía el comportamiento del embudo entre países?
4. ¿Cuál es la tasa de retención de los usuarios en D7, D14, D21 y D28?
5. ¿Qué cohortes presentan los mejores y peores niveles de retención?
6. ¿Existen diferencias relevantes de retención entre países?
7. ¿Qué etapas deberían considerarse prioritarias para una eventual optimización?

---

# 🔎 Etapas del análisis

El proyecto se desarrolló en varias etapas.

## 1. Análisis del embudo general

Se analizaron los siguientes eventos del proceso de compra:

```text
first_visit
    ↓
select_item
    ↓
add_to_cart
    ↓
begin_checkout
    ↓
add_shipping_info
    ↓
add_payment_info
    ↓
purchase
```

Las tasas de conversión se calcularon tomando como referencia la primera etapa (`first_visit`).

### Conversión general

| Etapa               | Conversión desde `first_visit` |
| ------------------- | -----------------------------: |
| `select_item`       |                         76.90% |
| `add_to_cart`       |                         11.01% |
| `begin_checkout`    |                          4.00% |
| `add_shipping_info` |                          2.42% |
| `add_payment_info`  |                          2.09% |
| `purchase`          |                          1.25% |

El principal punto de fricción se encuentra entre **`select_item` y `add_to_cart`**.

La conversión acumulada pasa de **76.90%** de los usuarios que seleccionan un producto a solamente **11.01%** que lo incorporan al carrito.

Esto representa una pérdida aproximada del **85.7% de los usuarios entre ambas etapas**, siendo el mayor salto de pérdida observado en el embudo.

---

## 2. Análisis del embudo por país

El embudo también fue segmentado por `country` para identificar diferencias entre mercados.

Algunos resultados relevantes:

| País      | Select item | Add to cart |  Purchase |
| --------- | ----------: | ----------: | --------: |
| Uruguay   |      81.82% |  **22.73%** | **4.55%** |
| Chile     |      78.35% |      17.53% |     1.03% |
| México    |      79.75% |      13.22% |     2.48% |
| Perú      |      84.55% |      10.00% |     1.82% |
| Ecuador   |      74.58% |      10.17% |     0.00% |
| Colombia  |      76.36% |       9.70% |     0.00% |
| Bolivia   |      80.65% |       9.68% |     3.23% |
| Paraguay  |      71.43% |       9.52% |     0.00% |
| Brasil    |      72.60% |       8.90% |     0.68% |
| Argentina |      75.00% |   **8.75%** |     1.25% |

Uruguay presenta la mayor conversión hacia `add_to_cart`, con **22.73%**, mientras que Argentina presenta la menor, con **8.75%**.

Estos resultados muestran que la pérdida en esta etapa no se comporta de manera idéntica en todos los mercados.

---

# 📅 3. Análisis de retención

La segunda parte del proyecto analiza la retención de usuarios en cuatro momentos:

* **D7:** 7 días después del registro.
* **D14:** 14 días.
* **D21:** 21 días.
* **D28:** 28 días.

La retención se calculó para cohortes mensuales y también se segmentó por país.

---

## 4. Retención por cohortes

Las cohortes correspondientes a enero-julio de 2025 presentan comportamientos relativamente estables.

| Cohorte |        D7 |       D14 |       D21 |      D28 |
| ------- | --------: | --------: | --------: | -------: |
| Enero   |     86.2% |     56.2% |     24.1% |     3.0% |
| Febrero |     86.8% |     56.0% |     24.6% |     2.7% |
| Marzo   | **87.7%** | **56.8%** | **26.6%** |     3.0% |
| Abril   |     87.2% |     53.9% |     23.0% |     2.0% |
| Mayo    |     86.0% |     54.5% |     26.2% |     3.0% |
| Junio   |     85.9% |     55.1% |     25.2% |     2.1% |
| Julio   |     86.4% |     56.4% |     25.9% |     2.7% |
| Agosto  | **70.8%** | **29.7%** |  **7.5%** | **0.2%** |

La cohorte de **marzo de 2025** presenta los valores más altos en D7, D14 y D21.

En contraste, la cohorte de **agosto de 2025** presenta una reducción considerable de la retención en todos los períodos analizados:

* D7: 70.8%
* D14: 29.7%
* D21: 7.5%
* D28: 0.2%

La diferencia respecto de las cohortes anteriores es suficientemente marcada como para justificar una investigación específica sobre lo ocurrido durante agosto.

---

# 🌎 5. Retención por país

La retención también presenta diferencias entre países.

| País      |        D7 |       D14 |       D21 |      D28 |
| --------- | --------: | --------: | --------: | -------: |
| Argentina |     85.1% |     52.3% |     22.5% |     1.8% |
| Bolivia   |     80.8% |     46.8% |     19.2% |     2.5% |
| Brasil    | **87.2%** |     54.4% |     24.4% |     2.5% |
| Chile     |     83.7% |     51.8% |     22.1% |     1.7% |
| Colombia  |     84.5% |     52.0% |     21.8% |     1.6% |
| Ecuador   |     79.1% |     50.0% |     20.6% |     2.5% |
| México    |     86.1% | **55.8%** | **25.5%** |     3.1% |
| Paraguay  |     80.9% |     49.1% |     22.1% |     2.1% |
| Perú      |     84.3% |     51.1% |     22.9% | **3.2%** |
| Uruguay   |     86.1% |     48.8% |     23.0% |     2.5% |

México presenta el mayor promedio de retención entre los países analizados.

En D28, **Perú alcanza el mayor porcentaje individual, con 3.2%**, seguido por México con 3.1%.

La mayor caída general de retención se observa entre **D21 y D28**, lo que indica una reducción muy significativa de usuarios activos durante la cuarta semana.

---

# 📋 Informe ejecutivo C → F → I

## Contexto

El análisis estudia el comportamiento de los usuarios de MercadoLibre durante el período comprendido entre el **1 de enero y el 31 de agosto de 2025**.

Se analizaron dos procesos:

1. El recorrido de los usuarios a través del embudo de compra.
2. La permanencia de los usuarios a lo largo del tiempo mediante análisis de cohortes.

Para el embudo se utilizaron los eventos:

`first_visit → select_item → add_to_cart → begin_checkout → add_shipping_info → add_payment_info → purchase`

La retención se analizó en D7, D14, D21 y D28.

---

## Hallazgos

### Embudo

La mayor fricción del embudo se encuentra entre:

```text
select_item → add_to_cart
```

La conversión acumulada disminuye desde **76.90% hasta 11.01%**, lo que representa una pérdida aproximada del **85.7% de los usuarios que habían seleccionado un producto**.

También existen diferencias importantes entre países.

Uruguay alcanza una conversión a `add_to_cart` de **22.73%**, mientras Argentina registra **8.75%**.

### Retención

Las cohortes de enero a julio presentan un comportamiento relativamente estable.

La cohorte de agosto constituye una excepción importante:

* D7: 70.8%
* D14: 29.7%
* D21: 7.5%
* D28: 0.2%

Esto representa una caída muy superior a la observada en las cohortes anteriores.

Por país, México presenta el mejor promedio general de retención, mientras Perú registra el mayor valor individual en D28, con **3.2%**.

---

## Implicaciones

### 1. Priorizar `add_to_cart`

La incorporación del producto al carrito debería ser una de las principales áreas de investigación y optimización.

Algunas variables que podrían investigarse son:

* Precio.
* Costos de envío.
* Disponibilidad del producto.
* Promociones.
* Condiciones de compra.
* Confianza del usuario.
* Información presentada antes de agregar el producto.
* Experiencia de usuario y facilidad de interacción.

### 2. Analizar las diferencias entre países

La diferencia entre mercados sugiere que puede ser útil estudiar qué factores están asociados con el mejor comportamiento observado en determinados países.

En particular, Uruguay puede utilizarse como referencia para investigar qué características del proceso favorecen su mayor conversión hacia `add_to_cart`.

### 3. Investigar la anomalía de agosto

La caída de la cohorte de agosto requiere una investigación específica.

Entre las posibles áreas de análisis se encuentran:

* Cambios en la adquisición de usuarios.
* Campañas de marketing.
* Calidad del tráfico.
* Cambios en el producto.
* Modificaciones del onboarding.
* Experiencia de usuario.
* Cambios en el comportamiento de los usuarios.
* Posibles problemas en la medición o definición de retención.

No debe asumirse una causa específica únicamente a partir de estos datos; sería necesario contrastar estas hipótesis con información adicional.

### 4. Analizar la pérdida de usuarios entre D21 y D28

La caída observada durante la cuarta semana indica que mantener la actividad del usuario después de las primeras tres semanas constituye un punto relevante para investigar.

Podrían evaluarse estrategias como:

* Notificaciones.
* Recordatorios personalizados.
* Incentivos.
* Recompensas.
* Recomendaciones personalizadas.
* Acciones destinadas a generar recurrencia.

---

# 💭 Reflexión personal

## ¿Qué etapa mejoraría primero?

La primera etapa que mejoraría sería **`add_to_cart`**.

La razón principal es que existe una diferencia muy grande entre los usuarios que muestran interés suficiente para seleccionar un producto y aquellos que efectivamente lo incorporan al carrito.

Antes de implementar una solución concreta, investigaría factores como precio, costos de envío, disponibilidad, promociones, confianza y experiencia de usuario para determinar qué está provocando esta pérdida.

---

## ¿Qué aprendí sobre el comportamiento del usuario?

Este análisis permitió observar que el comportamiento del usuario cambia considerablemente a medida que avanza por el proceso de compra.

Una gran cantidad de usuarios demuestra interés al seleccionar productos, pero una proporción mucho menor continúa hasta incorporarlos al carrito y posteriormente completar la compra.

También se observa que el comportamiento no es homogéneo entre países ni entre cohortes.

Las diferencias entre mercados muestran que las estrategias de optimización pueden requerir una perspectiva segmentada, mientras que la fuerte caída de la cohorte de agosto demuestra la importancia de analizar el comportamiento a lo largo del tiempo y no solamente mediante promedios generales.

El análisis de cohortes también permite detectar cambios que podrían quedar ocultos al observar únicamente los resultados agregados.

---

# 🛠️ Herramientas utilizadas

* **Microsoft Excel**
* Análisis de datos
* Tablas y métricas de conversión
* Segmentación por país
* Análisis de cohortes
* Análisis de retención

---

# 📌 Principales conclusiones

1. La mayor fricción del embudo se encuentra entre **`select_item` y `add_to_cart`**.
2. La conversión desde `first_visit` hasta `purchase` es de **1.25%**.
3. Existen diferencias relevantes en la conversión entre países.
4. Uruguay presenta la mayor conversión hacia `add_to_cart`, con **22.73%**.
5. Las cohortes de enero a julio muestran una retención relativamente estable.
6. La cohorte de agosto presenta una caída excepcional de retención.
7. México presenta el mejor promedio general de retención entre los países analizados.
8. Perú alcanza el mayor porcentaje de retención en D28, con **3.2%**.
9. La pérdida de usuarios entre D21 y D28 representa un punto importante para investigar.
10. Los resultados sugieren que la optimización debe considerar tanto las etapas del funnel como las diferencias entre mercados y cohortes.

---

## 📁 Estructura del análisis

El archivo de trabajo contiene las siguientes hojas:

```text
Informe Ejecutivo
├── Contexto
├── Hallazgos
├── Implicaciones
└── Reflexión personal

Embudo General
└── Conversión por etapa

Embudo General x Pais
└── Conversión segmentada por país

Retencion x Pais
└── Retención D7 / D14 / D21 / D28 por país

Retencion x Cohort
└── Retención D7 / D14 / D21 / D28 por cohorte
```

---

## 🎓 Aprendizaje principal

El principal aprendizaje del proyecto es que analizar únicamente una métrica global puede ocultar problemas importantes.

El análisis combinado de **embudo + país + cohortes + retención** permite identificar no solamente cuánto convierten o retienen los usuarios, sino también **en qué momento se pierden, en qué mercados ocurre y cómo cambia el comportamiento a lo largo del tiempo**.

Esto convierte los datos descriptivos en información útil para formular hipótesis de negocio y definir qué áreas deberían investigarse con mayor profundidad.

