# 📞 Análisis de Tarifas de Prepago de Megaline

Este proyecto tiene como objetivo analizar el comportamiento de los clientes de la empresa de telecomunicaciones **Megaline** y determinar cuál de sus dos tarifas de prepago —**Surf** o **Ultimate**— genera mayores ingresos. El análisis se basa en datos reales de 500 usuarios a lo largo de 2018.

## 🎯 Objetivo del proyecto

- Analizar el uso mensual de llamadas, mensajes y datos por parte de los clientes.
- Calcular los ingresos mensuales generados por cada usuario.
- Comparar los ingresos generados por cada plan tarifario.
- Evaluar si existen diferencias significativas mediante pruebas estadísticas.

---

## 🧾 Descripción de tarifas

| Tarifa   | Pago mensual | Minutos | SMS | Datos | Costo adicional (min/SMS/GB) |
|----------|--------------|---------|-----|-------|-------------------------------|
| **Surf**     | $20          | 500     | 50  | 15 GB | $0.03 / $0.03 / $10           |
| **Ultimate** | $70          | 3000    | 1000| 30 GB | $0.01 / $0.01 / $7            |

> 🔁 Llamadas se redondean hacia arriba a minutos completos.  
> 📶 Datos se redondean por mes hacia arriba al gigabyte más cercano (1 GB = 1024 MB).

---

## 📂 Conjunto de datos

Se utilizaron cinco tablas:

### `users.csv` — Información del cliente
- `user_id`: ID del usuario  
- `first_name`, `last_name`, `age`  
- `reg_date`, `churn_date`, `city`, `plan`  

### `calls.csv` — Registro de llamadas
- `id`, `call_date`, `duration`, `user_id`  

### `messages.csv` — Registro de mensajes SMS
- `id`, `message_date`, `user_id`  

### `internet.csv` — Sesiones web
- `id`, `mb_used`, `session_date`, `user_id`  

### `plans.csv` — Detalles de tarifas
- `plan_name`, `usd_monthly_fee`, `minutes_included`, `messages_included`, `mb_per_month_included`, `usd_per_minute`, `usd_per_message`, `usd_per_gb`  

---

## 🔍 Estructura del análisis

### 🛠 Paso 1: Exploración de datos
- Carga de archivos CSV
- Análisis general de estructura y tipos de datos

### 🧼 Paso 2: Preparación de los datos
- Conversión de formatos de fecha y tipo
- Limpieza de errores, valores ausentes y duplicados
- Cálculo mensual por usuario de:
  - Total de llamadas y minutos
  - Total de SMS enviados
  - Total de datos utilizados
  - Ingresos mensuales generados

### 📊 Paso 3: Análisis descriptivo
- Cálculo de media, varianza y desviación estándar por tarifa
- Histogramas de consumo mensual por tipo de servicio
- Comparación visual del comportamiento entre planes

### 🧪 Paso 4: Pruebas estadísticas
1. **¿El ingreso promedio difiere entre tarifas Surf y Ultimate?**
2. **¿El ingreso promedio en Nueva York y Nueva Jersey es distinto del resto del país?**

Se utilizó un valor de α definido por el analista y se siguió el método de prueba de hipótesis adecuado, especificando:
- Hipótesis nula (H₀) y alternativa (H₁)
- Elección del test estadístico (prueba de hipótesis para dos muestras)
- Resultados y conclusiones

---

## 📌 Resultados esperados

- Comportamientos diferenciados de consumo entre tarifas.
- Identificación de cuál plan genera más ingresos.
- Recomendaciones estratégicas para marketing o asignación presupuestaria.

---

## 🧰 Herramientas utilizadas

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib & Seaborn**
- **SciPy (para pruebas estadísticas)**
- **Jupyter Notebook**
---> Proyecto realizado como parte del desarrollo profesional en análisis de datos.
