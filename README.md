# Identificación de Fallas en Muestras de Acero — Minor en Ciencias de Datos

Proyecto de análisis de datos desarrollado en el marco del **Minor en Ciencias de Datos** (TIC I, Facultad de Ingeniería — Departamento de Ingeniería Informática), utilizando el conjunto de datos **Steel Plates Faults** del repositorio UCI (Semeion Research Center).

- **Autores:** Bastián Araya y Melisa González
- **Profesoras:** Isidora Abasolo y Marcela Rivera

---

## Estado y Hoja de Ruta del Proyecto

- **Entrega 1 (Completada):** Limpieza y auditoría de calidad del dataset, análisis exploratorio univariado, bivariado y multivariado, junto con pruebas de hipótesis estadísticas para caracterizar los defectos críticos.
- **Próxima Etapa (En desarrollo — plazo ~3 semanas):** Aplicación de modelos de **aprendizaje automático supervisado** (*Machine Learning*) sobre el mismo conjunto de datos para la clasificación automática de los tipos de fallas.

---

## Descripción del Problema y Dataset

El dataset reúne **1.941 observaciones** de defectos superficiales en placas de acero **A300** y **A400**, descritos mediante **27 variables independientes** (coordenadas de *bounding box*, área en píxeles, perímetros, espesor de placa, ancho de cinta transportadora, índices geométricos normalizados, escalamientos logarítmicos/sigmoides y métricas de luminosidad) y **7 categorías de falla**:

`Pastry` · `Z_Scratch` · `K_Scratch` · `Stains` · `Dirtiness` · `Bumps` · `Other_Faults`

Desde el punto de vista de control de calidad e integridad estructural, el estudio prioriza la detección de **`Z_Scratch`** (rasguños angulares en zig-zag) y **`K_Scratch`** (rayas longitudinales profundas), ya que sus geometrías agudas actúan como concentradores de esfuerzos capaces de provocar fracturas tempranas.

---

## Principales Hallazgos (Entrega 1)

- **Distribución univariada:** Predominan `Other_Faults` y `Bumps`, seguidas por `Z_Scratch` y `K_Scratch`, justificando el foco en estas dos últimas clases críticas.
- **Relaciones bivariadas y multivariadas:** El tipo de acero, el espesor de placa (`Steel_Plate_Thickness`), `Orientation_Index` y `Edges_Y_Index` discriminan eficazmente entre `Z_Scratch` y `K_Scratch`. Además, `K_Scratch` se concentra casi exclusivamente en acero **A400** (salvo un registro), mientras que `Z_Scratch` ocurre mayoritariamente en **A300**.
- **Inferencia estadística:** Los tests de hipótesis confirman que el espesor de placa y `Edges_Y_Index` son indicadores estadísticamente significativos para distinguir ambas fallas, condicionado al tipo de acero.

---

## Contenido del Repositorio

| Archivo / Carpeta | Descripción |
| :--- | :--- |
| [`Entrega1_Minor_DS.ipynb`](./Entrega1_Minor_DS.ipynb) | Notebook de Google Colab con el análisis exploratorio, visualizaciones, correlaciones y tests de hipótesis de la Entrega 1. |
| [`Presentacion_Entrega1_Minor_DS.md`](./Presentacion_Entrega1_Minor_DS.md) | Documento técnico con el marco conceptual, definición matemática de variables, objetivos, conclusiones y bibliografía. |
| [`assets/`](./assets/) | Figuras técnicas y diagramas de la presentación (incluyendo visualizaciones de defectos y esquemas de métricas). |

---

## Referencias Principales

- UCI Machine Learning Repository (2010). *Steel Plates Faults Data Set* (ID: 198). Semeion Research Center of Sciences of Communication, Rome, Italy.
- Buscema, M., Terzi, S., & Tastle, W. (2010). *A New Meta-Classifier*. NAFIPS 2010, IEEE, pp. 1–7.
- Gonzalez, R. C., & Woods, R. E. (2018). *Digital Image Processing* (4th ed.). Pearson.
- Neogi, N., Mohanta, D. K., & Dutta, P. K. (2014). *Review of vision-based steel surface inspection systems*. EURASIP Journal on Image and Video Processing, 2014(1), 50.
