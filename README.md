# Mejor Distrito de Madrid para Invertir en Vivienda Residencial

> *Análisis predictivo de revalorización inmobiliaria mediante técnicas de data engineering y machine learning*

---

## 📋 Descripción General

Este proyecto constituye el **Trabajo Final de Grado (TFG)** en el programa de doble titulación en Ingeniería Informática y Business Analytics de la **Universidad Francisco de Vitoria (UFV)**, realizado en colaboración con **SAS**.

El objetivo principal es **identificar el distrito de la Comunidad de Madrid con mayor potencial de revalorización de vivienda residencial**, utilizando análisis riguroso de datos históricos (2016-2023) e indicadores socioeconómicos de múltiples fuentes públicas.

### 🎯 Hallazgo Principal

**Fuencarral-El Pardo** emerge como el distrito con mayor potencial de revalorización, con una **proyección del 3.88%** de apreciación esperada, impulsado por:
- Alto nivel educativo de la población
- Baja densidad poblacional
- Amplias zonas verdes
- Renta per cápita elevada
- Proyecto de desarrollo Madrid Nuevo Norte

---

## 🛠️ Arquitectura y Metodología

### Fases del Proyecto

```
┌─────────────────────────────────────────────────────────────┐
│  1. INGENIERÍA DEL DATO (Data Engineering)                 │
│     ├─ Extracción (ETL)                                    │
│     ├─ Transformación y limpieza                           │
│     └─ Consolidación en base de datos unificada            │
│                                                              │
│  2. ANÁLISIS DEL DATO (Data Analysis)                      │
│     ├─ Exploración estadística                             │
│     ├─ Entrenamiento de modelos                            │
│     └─ Validación y comparación de métricas                │
│                                                              │
│  3. ANÁLISIS DE NEGOCIOS (Business Analysis)               │
│     ├─ Respuesta a preguntas de investigación              │
│     ├─ Generación de insights                              │
│     └─ Recomendaciones estratégicas                        │
└─────────────────────────────────────────────────────────────┘
```

### Stack Tecnológico

| Componente | Herramientas |
|-----------|-------------|
| **Almacenamiento & Cálculos** | Excel |
| **Ingeniería de Datos** | Python 3, Pandas, NumPy |
| **Modelado & ML** | Scikit-Learn, Statsmodels |
| **Visualización** | Matplotlib, Seaborn, Power BI |
| **Datos** | Ayuntamiento de Madrid, Idealista, INE |

---

## 📊 Fuentes de Datos

### Período de Análisis: 2016 - 2023 (8 años)

#### Datos Demográficos
- **Fuente**: Ayuntamiento de Madrid
- **Variables**: 237 variables iniciales → 45 variables procesadas
- **Categorías**:
  - Características generales del distrito
  - Población y densidad
  - Indicadores económicos
  - Indicadores de desempleo
  - Educación y calidad de vida
  - Seguridad y servicios municipales

#### Datos Inmobiliarios
- **Fuente**: Idealista (portal inmobiliario)
- **Variables**:
  - Precio medio de venta (€/m²)
  - Precio medio de alquiler (€/m²)
  - Número de viviendas disponibles
  - Variaciones mensuales y anuales

#### Datos Macroeconómicos
- **Fuente**: INE + Datosmacro
- **Variables**:
  - PIB anual y per cápita
  - Valor Euribor
  - Tipos de interés hipotecarios (variable/fijo/total)

---

## 🔍 Modelos Estadísticos Implementados

### 1. **LASSO Regression**
- **Propósito**: Selección de características y regularización L1
- **RMSE**: 703.88 € | **R²**: 0.56 | **MAE**: 339.46 €

### 2. **RIDGE Regression**
- **Propósito**: Regularización L2 para estabilidad
- **RMSE**: 280.69 € | **R²**: 0.93 | **MAE**: 179.08 €
- ⭐ **Mejor rendimiento general**

### 3. **Random Forest Regressor**
- **Propósito**: Captura de relaciones no lineales e interacciones
- **RMSE**: 280.69 € | **R²**: 0.65 | **MAE**: 287.35 €

### Comparativa de Métricas

| Modelo | RMSE | R² | MAE |
|--------|------|-----|-----|
| LASSO | 703.88 | 0.56 | 339.46 |
| **RIDGE** | **280.69** | **0.93** | **179.08** |
| Random Forest | 280.69 | 0.65 | 287.35 |

---

## 📈 Principales Hallazgos

### Top 3 Distritos por Revalorización Esperada

| Rank | Distrito | Precio Venta (€/m²) | Revalorización (%) |
|------|----------|-------------------|------------------|
| 🥇 | Fuencarral-El Pardo | 3,437 | 3.88% |
| 🥈 | Retiro | 4,308 | 3.46% |
| 🥉 | Villaverde | 1,706 | 2.83% |

### Variables Más Influyentes en la Revalorización

1. **Precio medio alquiler (€/m²)** - Coeficiente: +800
2. **Nivel de estudios** - Correlación positiva fuerte
3. **Centros privados concertados** - Indicador de calidad educativa
4. **Extranjeros** - Diversidad demográfica
5. **Renta disponible bruta per cápita** - Factor económico

### Insights Demográficos

- **Densidad poblacional**: Inversamente correlacionada con revalorización
- **Educación**: Distritos con mayor nivel educativo muestran mejor potencial
- **Zonas verdes**: Fuencarral-El Pardo lidera en hectáreas de espacios verdes (3.1 mil Ha)
- **Calidad de vida**: Fuencarral-El Pardo alcanza puntuación de 520 en índice de calidad de vida

---

## 🚀 Cómo Usar Este Proyecto

### Requisitos Previos

```bash
Python 3.8+
Jupyter Notebook
pip (gestor de paquetes)
```

### Instalación

```bash
# Clonar el repositorio
git clone https://github.com/juan-fernandez-cerezo/TFG-BA.git
cd TFG-BA

# Crear entorno virtual (opcional pero recomendado)
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt
```

### Ejecución del Análisis

```bash
# Abrir Jupyter Notebook
jupyter notebook Codigo_TFG.ipynb

# Ejecutar todas las celdas en orden:
# 1. CARGA DE LOS DATOS
# 2. REGRESION LASSO
# 3. REGRESION RIDGE
# 4. RANDOM FOREST REGRESSOR
```

### Estructura de Archivos

```
TFG-BA/
├── Codigo_TFG.ipynb              # Notebook principal con análisis y modelos
├── Defensa.pdf                   # Presentación de defensa del TFG
├── Distritos.xlsx                # Dataset consolidado (2016-2023)
├── requirements.txt              # Dependencias de Python
├── README.md                      # Este archivo
└── data/                          # (Opcional) Datos fuente sin procesar
    ├── madrid_demografics.xlsx
    ├── idealista_precios.xlsx
    └── ine_economic_indicators.xlsx
```

---

## 📊 Visualizaciones Principales

El proyecto incluye múltiples visualizaciones interactivas:

- **Mapa de revalorización positiva/negativa** por distrito
- **Evolución histórica de precios** (2016-2023) por zona
- **Comparativa de indicadores demográficos** (densidad, educación, zonas verdes)
- **Correlación de variables** influyentes en revalorización
- **Importancia de características** según Random Forest
- **Predicciones vs valores reales** para validación de modelos

Disponibles en:
- Código Python (Matplotlib, Seaborn)
- Power BI Dashboard (análisis interactivo)

---

## 💡 Recomendaciones de Inversión

### Para Inversores

1. **Horizonte de inversión a largo plazo**: Fuencarral-El Pardo muestra potencial sostenido
2. **Factores de riesgo**: Monitorear indicadores de desempleo y tipos de interés
3. **Valor añadido**: Considerar proximidad al proyecto Madrid Nuevo Norte
4. **Diversificación**: Retiro como opción alternativa con mayor estabilidad

### Limitaciones del Análisis

- Datos históricos hasta 2023; mercado inmobiliario es dinámico
- No se consideran factores externos imprevistos (crisis económicas, cambios legislativos)
- Validación del modelo requiere datos de años posteriores
- Correlación ≠ causalidad en todos los casos

---

## 👤 Autor

**Juan Fernández Cerezo**
- Computer Engineering Student (Ingeniería Informática + Business Analytics)
- Universidad Francisco de Vitoria (UFV), Madrid
- Digital Engineering Intern, EY Madrid (Sept 2025-)
- Focus: Data Engineering, Machine Learning, Cloud Infrastructure

📧 Contacto: [Tu correo]  
🔗 Portfolio: [Tu enlace de portfolio]

---

## 🎓 Supervisión y Colaboración

- **Supervisor**: [Nombre del supervisor]
- **Universidad**: Universidad Francisco de Vitoria
- **Institución Colaboradora**: SAS

---

## 📄 Licencia

Este proyecto está licenciado bajo [Especificar licencia - ej. MIT, CC-BY-4.0]

---

## 🔗 Referencias y Recursos

### Fuentes de Datos

- [Ayuntamiento de Madrid - Portal de Datos](https://www.madrid.es)
- [Idealista - Base de datos inmobiliaria](https://www.idealista.com)
- [INE - Instituto Nacional de Estadística](https://www.ine.es)
- [Datosmacro - Indicadores económicos](https://www.datosmacro.com)

### Lecturas Recomendadas

- Scikit-Learn Documentation: Regression Models
- Time Series Analysis in Real Estate Markets
- Feature Engineering for Housing Price Prediction

---

## 📝 Notas

- **Última actualización**: 16/07/2024
- **Versión**: 1.0
- **Estado**: Proyecto completado ✅

---

**Resumen ejecutivo**: Este análisis proporciona una base sólida y fundamentada en datos para tomar decisiones de inversión inmobiliaria en Madrid, considerando múltiples dimensiones socioeconómicas y proyecciones futuras.

Para más detalles técnicos, consultar la presentación `Defensa.pdf`.
