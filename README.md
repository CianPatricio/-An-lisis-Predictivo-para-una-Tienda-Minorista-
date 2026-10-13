# 🛒 Análisis Predictivo para una Tienda Minorista

Proyecto de ciencia de datos que predice las **ventas diarias** de una tienda minorista a partir del día de la semana, las promociones y los días festivos, comparando tres modelos de regresión con Python y scikit-learn.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626)

---

## 📌 Objetivo

Construir un modelo capaz de estimar cuánto va a vender la tienda cada día, para apoyar decisiones de **inventario, planificación de personal y marketing**.

## 📂 Dataset

Archivo `Ventas (1).csv` con **365 registros diarios (enero a diciembre de 2022)** y sin valores faltantes.

| Columna | Descripción |
|---|---|
| `Fecha` | Fecha del registro (2022-01-01 a 2022-12-31) |
| `DíaDeLaSemana` | Día de la semana, de 1 (lunes) a 7 (domingo) |
| `Promociones` | 1 si hubo promoción ese día, 0 si no (alrededor del 20% de los días) |
| `Festivo` | 1 si fue día festivo, 0 si no (alrededor del 14% de los días) |
| `Ventas` | Ventas del día (variable a predecir; promedio cercano a 2.997) |

## 🔄 Metodología

1. **Preparación de datos**: revisión de nulos, conversión de `Fecha` a `datetime`, normalización de las variables con `MinMaxScaler` y división 80% entrenamiento / 20% prueba (`random_state=42`).
2. **Análisis exploratorio (EDA)**: estadísticas descriptivas, distribución de ventas, ventas promedio por día de la semana y boxplots del efecto de promociones y festivos (incluida su interacción).
3. **Selección de modelo**: comparación de Regresión Lineal, Árbol de Decisión y Random Forest usando R² sobre el conjunto de prueba.
4. **Evaluación**: gráficos de ventas reales vs. predichas (dispersión y serie temporal) con el modelo elegido.
5. **Conclusiones y recomendaciones** para el negocio.

## 📊 Resultados

| Modelo | R² (prueba) |
|---|---|
| Regresión Lineal | 0.9924 |
| Árbol de Decisión | 0.9924 |
| Random Forest | 0.9923 |

Los tres modelos rinden prácticamente igual, por lo que se eligió la **Regresión Lineal** por ser la más simple e interpretable. El gráfico de ventas reales vs. predichas muestra una fuerte relación positiva, con algunos días donde la predicción se aleja del valor real (posibles eventos no capturados por las variables).

## 💡 Recomendaciones para el negocio

- **Inventario**: reforzar el stock en fechas festivas para evitar faltantes.
- **Personal**: ajustar los turnos según los días festivos y el día de la semana, más que según las promociones.
- **Marketing**: dirigir campañas a los períodos de ventas más fuertes.
- **Anomalías**: investigar los días con grandes diferencias entre ventas reales y predichas.
- **Mejoras del modelo**: sumar variables como clima, eventos locales, competencia o datos económicos.

## 🚀 Cómo ejecutarlo

```bash
# 1. Clonar el repositorio
git clone https://github.com/<tu-usuario>/<nombre-del-repo>.git
cd <nombre-del-repo>

# 2. Instalar dependencias
pip install pandas matplotlib seaborn scikit-learn openpyxl jupyter

# 3. Abrir el notebook
jupyter notebook "_Análisis_Predictivo_para_una_Tienda_Minorista_.ipynb"
```

> Asegurate de que `Ventas (1).csv` esté en la misma carpeta que el notebook.

## 🛠️ Tecnologías

Python · pandas · matplotlib · seaborn · scikit-learn · Jupyter Notebook


