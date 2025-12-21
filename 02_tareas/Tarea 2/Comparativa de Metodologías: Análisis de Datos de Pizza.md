 ## 📊 Comparativa de Metodologías: Análisis de Datos de Pizza
Este análisis explica por qué tres modelos de IA, utilizando el mismo archivo fuente, llegaron a resultados tan dispares (desde 113 hasta 282 pizzas).

### 1. Resumen de Ejecución Técnica
La principal diferencia radica en la capacidad de extracción y el tratamiento estadístico de la incertidumbre.


| Fase | **Claude** (Enfoque Programático/Extensivo)| **Copilot** (Enfoque Scripting/Estandarizado) | **Gemini** (Enfoque Estadistico/Muestral) |
| ------ | ------ | ------ | ------|
| **Extracción** | Parsing mediante Regex y lógica de JS| Uso de librerías de Python (PyPDF2) y Regex | Identificación de patrones en 41 fuentes fragmentarias
| **Limpieza** | Normalización de "Veggi" y validación de rangos (0-15) | Lowercasing y corrección tipográfica profunda (olives/olivess) | Estandarización de categorías y filtrado de ruido (etiquetas de fuente)|
| **Muestra Final**| **588** registros (492 válidos) | **516 registros** (444 válidos) | **Muestra parcial** (Foco en frecuencias y moda) |
| **Margen de Seguridad** | **20%** (Factor de seguridad alto) | **10%** (Buffer de variabilidad) | **10%** (Margen de error sugerido)|
| **Resultado Final** | **282 pizzas** | **238** pizzas | **113 pizzas** (+10% opcional)|

## 2. Divergencias en la Metodología de Procesamiento

🧐 **¿Por qué los resultados son tan diferentes?**
La disparidad en los números (de 113 a 282 pizzas) no se debe a un error de cálculo matemático simple, sino a la interpretación de los datos crudos y la capacidad de extracción:

#### 1. Capacidad de Ingesta (El factor principal)

- **Claude** parece haber logrado la extracción más completa del PDF, identificando 588 líneas de datos. Al tener más "personas" en su base de datos, la suma total de rebanadas es naturalmente más alta. Utilizó un parser de texto plano. Al reportar 588 registros, es el que logró la lectura más profunda del archivo, capturando líneas que otros modelos ignoraron por errores de formato o saltos de página.

- **Copilot** detectó 516 registros. Es probable que su script de Python haya omitido páginas o líneas donde el formato del PDF era menos amigable para la librería PyPDF2. Al usar librerías de Python (PyPDF2), es más rígido. Si el PDF tenía errores de codificación en ciertas páginas, el script simplemente saltó esos datos, resultando en 516 registros.

- **Gemini** parece haber realizado un análisis basado en una muestra representativa o una extracción parcial de las "fuentes" que logró identificar, lo que explica por qué su conteo total de rebanadas (884) es mucho menor al de Claude (1,877). Interpretó el documento como "41 fuentes". Esto sugiere que analizó bloques de datos o fragmentos, sumando un total de 884 rebanadas, lo que representa menos de la mitad de lo capturado por Claude.

Esta es la diferencia más crítica. Los PDF no son bases de datos; son capas de texto que la IA debe "reconstruir".

#### 2. Lógica de Limpieza (Normalización de Variables)

1. El dataset contenía errores humanos ("Veggi" vs "Veggie"). La forma de agruparlos cambia el inventario por sabor:

- Normalización Agresiva (Copilot): Usó expresiones regulares (re.sub) para corregir incluso "olive/olivess". Esto concentra la demanda en menos categorías, haciendo el pedido más eficiente.

- Normalización Lógica (Claude/Gemini): Se centraron en las variantes más obvias ("Veggi").

- Impacto: Si no agrupas correctamente, terminas pidiendo 5 pizzas de "Veggi" y 5 de "Veggie" por separado, lo que altera la logística de pedidos a la pizzería.

2. Tratamiento de los "No Consumidores"
**Claude** y **Copilot** restaron a los "I don't like pizza" del total para calcular el promedio de consumo, pero los mantuvieron en la estadística de "población total".

La diferencia en el conteo de estos sujetos (96 en Claude vs. 72 en Copilot) altera el denominador de cualquier promedio calculado.

#### 3. El Tratamiento de los "Outliers" (Casos Extremos) 

Aquí es donde Claude se diferencia significativamente en su análisis:

- **Detección de "Superconsumidores":** Claude notó que los amantes de las aceitunas consumen **9.46 rebanadas** cada uno. Si un modelo no detecta este "nicho" de alto consumo y solo usa el promedio general, pedirá menos pizzas de las necesarias para ese grupo específico.

- **El Error del Promedio Simple:** Si un modelo (como Gemini) usa un promedio general de 3.8 rebanadas para todos, **se quedaría sin pizza de aceitunas a mitad del evento,** porque ese grupo específico come el doble que el resto.

- **Análisis de Perfiles:** Claude segmentó en "Ligero, Moderado y Alto", mientras que los otros trataron a la masa de gente como un bloque uniforme. 

#### 4. Modelado de Incertidumbre (Margen de Seguridad)
Las metodologías revelan diferentes "personalidades" de gestión de riesgo:

| Modelo | Margen| Filosofía |
| ------ | ------ | ------ |
| **Claude**| **20%** | **Conservadora:** "Es preferible que sobre pizza a enfrentar el costo social de que alguien se quede con hambre".
| **Copilot** | **10%** | **Optimista/Técnica:** Confia en que la desviación estándar de la muestra es baja y el buffer suficiente |
|**Gemini**|**10%**|**Sugerida:** No lo integra directamente en el cálculo base, sino que lo deja como una recomendación externa.

#### 5. Conclusiones
1. **Ingesta Irregular:** El PDF no fue leído con la misma precisión por todos; Claude extrajo ~14% más datos que Copilot.

2. **Limpieza de Texto:** Copilot fue el más preciso unificando términos erróneos (ej. "olivess"), lo que depura la lista de compras.

3. **Filosofía de Riesgo:** Claude prioriza la disponibilidad, mientras que Copilot y Gemini priorizan la optimización.

