
# Informe de análisis de datos de pizza

Fuente: "Insights from Data and AI L2 - Dataset - Pizza Slice Data.docx"

## Resumen del conjunto de datos
- Total de registros: **516**
- Suma exacta de rebanadas declaradas: **1,934**
- Promedio de rebanadas por persona: **3.75**
- Mediana: **3** | Mínimo: **0** | Máximo: **12**
- Registros con etiqueta "No me gusta la pizza": **72** (rebanadas sumadas: **208**)

## Tendencias observadas
- **Sabores más frecuentes** (por número de respuestas):

| sabor               |   registros |
|:--------------------|------------:|
| Pepperoni           |         186 |
| Cheese              |         119 |
| No me gusta la pizza|          72 |
| Mushroom            |          63 |
| Veggie              |          47 |
| Olives              |          19 |
| Sausage             |          10 |

- **Consumo estimado por sabor (excluyendo "No me gusta la pizza")**:

| sabor     |   rebanadas_total |   registros |   participacion |
|:----------|-------------------:|------------:|----------------:|
| Pepperoni |                778 |         148 |           0.450 |
| Cheese    |                444 |          93 |           0.257 |
| Mushroom  |                186 |          53 |           0.108 |
| Veggie    |                160 |          41 |           0.093 |
| Olives    |                144 |          35 |           0.083 |
| Sausage   |                 14 |           4 |           0.008 |

## ¿Cuánta pizza deberíamos pedir?
- Supuesto: **8 rebanadas por pizza**.
- Opción A (excluyendo quienes dicen "No me gusta la pizza"): **1,726** rebanadas → **216** pizzas.
- Opción B (incluyendo a todos): **1,934** rebanadas → **242** pizzas.

### Pedido recomendado por sabor (Opción A)
| sabor     |   pizzas |   rebanadas_estimadas |
|:----------|---------:|----------------------:|
| Pepperoni |       97 |                   776 |
| Cheese    |       55 |                   440 |
| Mushroom  |       22 |                   176 |
| Veggie    |       20 |                   160 |
| Olives    |       18 |                   144 |
| Sausage   |        4 |                    32 |

> Nota: la asignación se hace según la participación en rebanadas consumidas por sabor (método de restos mayores). Ajusta si hay restricciones dietarias o tamaños de pizza distintos.

## Consideraciones de limpieza de datos
- Se unificó la ortografía **"Veggi"/"Veggie"** y se tradujo **"I don't like pizza"** a **"No me gusta la pizza"**.
- El archivo contiene repeticiones y bloques concatenados; el parser extrae cualquier patrón "número + etiqueta" válido.
- Si se desea excluir completamente a quienes indicaron- Si se desea excluir completamente a quienes indicaron "No me gusta la pizza", usa la Opción A.

