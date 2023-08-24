[`<p align=center><img src=imagenes/inversion.jpg>``<p>`]

<h1 align=center>**Analisis de Criptomonedas**</h1>

 Este repositorio es un proyecto individual cuyo objetivo es el analizis del mercado de las criptomonedas utlizando datos de la API CoinGecko.

En el jupiter notebook se puden encontrar los analasis y tranformaciones del los datos obtenidos de la API CoinGecko

En primer lugar se seleccionaron las 10 mejores criptomonedas en la APICoinGecko con el parametro {'vs_currency': 'usd', 'order': 'market_cap_desc', 'per_page': 10}.
Con el cual obtuve las 10 mejores criptomonedas actualmente.
Luego tome los datos de dichas criptomonedas en el lapso de estos ultimos 10 años, para ello se crearon 3 daaset para el valor del precio , el volumen y la capitalizacion para cada dia de los ultimos 10 años.
y por ultimo se creo un dataset adicional con la cotizacion en pesos argentinos de la precio de las criptomonedas a lo largo del tiempo para un analicis suplementario.

Las 10 Criptomonedas seleccionadas son:

<p align=center><h2>Bitcoin (BTC)</h2><img src=https://assets.coingecko.com/coins/images/1/large/bitcoin.png?1547033579><p>

<p align=center><h2>Staked-Ether (STETH)</h2><img src=https://assets.coingecko.com/coins/images/13442/large/steth_logo.png?1608607546><p>

<p align=center><h2>Ethereum (ETH)</h2><img src=https://assets.coingecko.com/coins/images/279/large/ethereum.png?1595348880><p>

<p align=center><h2>Tether (USDT)</h2><img src=https://assets.coingecko.com/coins/images/325/large/Tether.png?1668148663><p>

<p align=center><h2>Solana (SOL)</h2><img src=https://assets.coingecko.com/coins/images/4128/large/solana.png?1640133422><p>

<p><h2>Ripple (XRP)</h2><img src=https://assets.coingecko.com/coins/images/44/large/xrp-symbol-white-128.png?1605778731><p>

<p><h2>Dogecoin (DOGE)</h2><img src=https://assets.coingecko.com/coins/images/5/large/dogecoin.png?1547792256><p>

<p><h2>USD-Coin (USDC)</h2><img src=https://assets.coingecko.com/coins/images/6319/large/USD_Coin_icon.png?1547042389><p>

<p><h2>Binancecoin (BNB)</h2><img src=https://assets.coingecko.com/coins/images/825/large/bnb-icon2_2x.png?1644979850><p>

<p><h2>Cardano (ADA)</h2><img src=https://assets.coingecko.com/coins/images/975/large/cardano.png?1547034860><p>

Se realizaron algunas transformaciones a los datasets originales tales como:

+ Se reescalaron los valores en los dataset volumen y capitalizacion en parte por millon para que sean mas manejables los nuemeros
+ Fecha de lanzamiento: Como en la api no estaban completos tuve que agregarlas manualmente.
+ De https://es.investing.com/currencies/usd-ars-historical-data obtuve el historial de 10 años del peso con respecto al dolar
+ Nulos. El tratamiento de los valores nulos rellenaron por interpolacion
+ Se creó la columna con el retorno de inversión, llamada **`return`** como resultado de la relación entre con los campos **`revenue`** y **`budget`**. En los casos que la división no fue posible, se asignó el valor **`0`**.
+ Las columnas que no se utilizaron para en esta primera versión de la API, fueron eliminadas; a saber: **`video`**,**`imdb_id`**,**`adult`**,**`original_title`**,**`poster_path`** y **`homepage`**.
+ Los datasets fueron combinados a partir del campo **`id`**.
+ Se creó la variable **`recs`**, la cual contiene una lista de películas similares y que es utilizada por la API para el sistema de recomendación. La similaridad entre películas fue calculada a partir de una matriz de similaridad coseno utilizando la frecuencia de términos-frecuencia inversa del documento (**`tf-idf`**) en los campos **`title`** y **`overview`**.
+ Con la intención de volver más eficientes las consultas, se crearon datasets particulares para cada función de la API.

Estas tareas se realizaron en una [Jupyter Notebook](https://github.com/smlopez30/Proyecto-individual-Parte-1) con VSS Code y se subieron a GitHub. Se utilizaron librerías como Pandas, Numpy, Json, Matplotlib.pyplot y Scikit-learn.

por problemas de tamaño para subir el archivo credits.csv el mismo esta en el siguiente [link](https://mega.nz/file/gQ01DJQI#eUGE9q59kS4C5aiGj98xOrLPU0Jw_-D1hk-5RwkGgyg), ya que el mismo no se encuentra en Github

**`Análisis exploratorio de los datos`**: _(Exploratory Data Analysis-EDA)_

**Recopilación de Datos**

- Usar la API de CoinGecko para recopilar datos relevantes de las 10 criptomonedas seleccionadas, incluyendo precios, volumen de comercio, capitalización de mercado e información histórica.
- **EDA (Exploratory Data Analysis)**
- Inspección inicial de los datos: tipos de datos, dimensiones, primeras filas, etc.
- Búsqueda de valores faltantes y estrategia de manejo.
- Identificación y tratamiento de valores atípicos/extremos.
- Verificación de registros duplicados.
- Análisis descriptivo y visualización:

  - Distribución de precios, volumen, y capitalización de mercado.
  - Tendencias y patrones en el tiempo.
  - Relaciones entre las variables.

**Paso 4: Creación de Dashboard Interactivo**

- Diseño e implementación de un dashboard interactivo utilizando una herramienta de visualización (p.ej., Power BI).
- Inclusión de filtros que permitan a los usuarios explorar los datos de cada criptomoneda seleccionada.
- Representación visual clara y efectiva de los KPIs.

**Paso 5: Definición y Visualización de KPIs**

- KPI 1: Rentabilidad Histórica (calculada como el cambio porcentual en el precio durante un período determinado).
- KPI 2: Volatilidad (desviación estándar de los rendimientos diarios durante un período determinado).
- KPI 3: Volumen de Comercio Relativo (compara el volumen de comercio de una criptomoneda con su capitalización de mercado).
- Explicación y análisis de estos KPIs en el contexto del mercado de criptomonedas.

**Paso 6: Análisis y Recomendaciones**

- Derivar insights de los datos y visualizaciones.
- Formular recomendaciones basadas en el análisis, como estrategias de inversión, gestión del riesgo, y cómo seguir monitoreando el mercado.

**Paso 7: GitHub y Documentación**

- Crear un repositorio de GitHub que contenga todos los archivos y códigos utilizados en el proyecto.
- Incluir un archivo README que presente el proyecto de forma general y detalle lo que hay en cada archivo/carpeta.
- Incluir un reporte de análisis basado en los dashboards y los KPIs sugeridos.

**Desafíos adicionales:**

- Crear una base de datos en un motor SQL, ingestar el CSV procesado y utilizarla como fuente de datos del dashboard.
- Ejecutar scripts de Python en la herramienta de visualización de datos escogida.
- Realizar cruce de datos con datasets complementarios para enriquecer el análisis.

**Nota:** Es fundamental que cada uno de estos pasos esté bien documentado, tanto en el código (comentarios) como en las celdas Markdown del notebook (explicaciones y conclusiones), y en el README del repositorio de GitHub. El análisis debe ser claro y las recomendaciones deben estar fundamentadas en los datos.

 El principal atractivo que han tenido siempre, y que seguirán teniendo las criptomonedas, es que su potencial de ganancias es muy alto. Algunas de ellas, como es el caso del Bitcoin, han experimentado un aumento significativo en su valor. Esto ha generado muchas ganancias para los inversores que compraron bitcoin a precios bajos.

Sin embargo, es importante recordar que el valor de las criptomonedas así como sube también puede bajar. O sea que las ganancias no están garantizadas.

Los valores que has proporcionado parecen ser la volatilidad anualizada de varias criptomonedas, expresadas en términos porcentuales (es decir, multiplicadas por 100). En finanzas, la volatilidad es una medida común de riesgo y se usa ampliamente para comparar la estabilidad de diferentes activos. A continuación, te explico cómo interpretar estos números y qué podrías hacer a continuación con esta información:

**Interpretación de la Volatilidad Anualizada:**

1. **Bitcoin (0.558326)**: Esta volatilidad sugiere que se espera que el precio de Bitcoin fluctúe aproximadamente un 55.83% arriba o abajo durante un año, bajo condiciones de mercado normales. Es relativamente volátil comparado con monedas fiduciarias, pero es considerado uno de los criptoactivos más estables en comparación con otras criptomonedas.
2. **Ethereum (0.728804)**: La volatilidad de Ethereum es más alta que la de Bitcoin. Esto sugiere que Ethereum es, en términos relativos, más arriesgado que Bitcoin, pero también podría ofrecer mayores rendimientos potenciales.
3. **Tether (0.038778) y USD-Coin (0.047841)**: Estas son criptomonedas estables (stablecoins), y su volatilidad es muy baja en comparación con otras criptomonedas. Están diseñadas para mantener un valor estable y se utilizan comúnmente como refugio seguro cuando las otras criptomonedas son muy volátiles.
4. **Dogecoin (2.184709)**: Esta es una de las criptomonedas más volátiles de la lista. Su precio puede fluctuar muy significativamente, lo que la convierte en una inversión muy arriesgada, pero también con un potencial de retorno muy alto.
5. **Solana (1.116654)**: Solana ha experimentado un aumento en su volatilidad, lo que podría deberse a su crecimiento y adopción rápidos.

**¿Qué puedes hacer con esta información?**

1. **Gestión de Riesgos**: Si eres un inversor, podrías usar estos números para ajustar tu cartera de inversiones. Por ejemplo, si buscas menor riesgo, podrías optar por una mayor proporción de criptomonedas estables en tu cartera.
2. **Oportunidades de Inversión**: Si estás buscando mayores rendimientos y estás dispuesto a aceptar más riesgos, podrías invertir en criptomonedas con volatilidades más altas. Sin embargo, es crucial que investigues más y estés consciente de los riesgos.
3. **Estrategias de Trading**: Los traders a menudo buscan activos volátiles para estrategias a corto plazo, como el trading diario. Las criptomonedas con alta volatilidad, como Dogecoin y Solana en tu lista, podrían ser atractivas para los traders.
4. **Diversificación**: Puedes usar esta información para diversificar tu cartera, mezclando activos con diferentes niveles de volatilidad para lograr un equilibrio entre riesgo y rendimiento.

Recuerda que la volatilidad es solo una medida de riesgo y no debe ser la única métrica considerada al tomar decisiones de inversión. Es importante también considerar otros factores, como fundamentos del proyecto, adopción, equipo de desarrollo, entre otros, y, si es posible, consultar con un asesor financiero.

Para determinar qué criptomonedas del dataset son las mejores para invertir y en qué periodo, necesitamos definir algunas métricas y criterios. A continuación, te presento un enfoque paso a paso para llegar a una decisión informada, utilizando también las columnas `volumen_historico` y `capitalizacion_historica`:

1. **Definir una Métrica de Rentabilidad:**

   - Una métrica común es el Retorno de la Inversión (ROI), que ya has calculado. Podrías considerar usar el ROI anual promedio para cada criptomoneda.
2. **Considerar la Volatilidad:**

   - La inversión en criptomonedas puede ser muy volátil. Una forma de medir la volatilidad es calcular la desviación estándar del ROI.
   - Una inversión con menor volatilidad podría ser considerada más segura, aunque potencialmente con menores rendimientos.
3. **Examinar el Volumen de Negociación:**

   - Una criptomoneda con un alto volumen de negociación histórico (`volumen_historico`) generalmente indica liquidez y demanda.
4. **Evaluar la Capitalización de Mercado:**

   - La capitalización de mercado (`capitalizacion_historica`) también puede ser un buen indicador. Las criptomonedas con una alta capitalización de mercado son generalmente consideradas más estables.
5. **Establecer un Período de Inversión:**

   - Define si estás buscando invertir a corto, mediano o largo plazo y elige el periodo de ROI que mejor se ajuste a este horizonte (mensual, trimestral, semestral, anual).
6. **Filtrar y Ordenar:**

   - Con las métricas definidas en los pasos 1-4, puedes filtrar las criptomonedas que cumplen con ciertos criterios (por ejemplo, un mínimo ROI anual promedio y un máximo nivel de volatilidad) y luego ordenarlas en base a estas métricas para encontrar las "mejores" opciones.
7. **Analizar Gráficamente:**

   - Genera gráficos para visualizar estas métricas a lo largo del tiempo para cada criptomoneda. Esto te puede dar una idea de las tendencias y la estabilidad.
8. **Decidir en Base a Tu Perfil de Riesgo:**

   - No todas las inversiones son adecuadas para todos los inversores. Asegúrate de que tu elección se alinee con tu tolerancia al riesgo y tus objetivos financieros.

Aquí hay un ejemplo de cómo podrías implementar algunos de estos pasos en Python:

```python
# Calcular la media y la desviación estándar del ROI anual
criptomoneda['mean_roi_anual'] = criptomoneda['roi_anual'].mean()
criptomoneda['std_roi_anual'] = criptomoneda['roi_anual'].std()

# Filtrar criptomonedas que tienen un ROI anual promedio positivo y una volatilidad relativamente baja
criptos_filtradas = criptomoneda[(criptomoneda['mean_roi_anual'] > 0) & (criptomoneda['std_roi_anual'] < 0.2)]

# Ordenar por ROI anual promedio y capitalización de mercado
criptos_ordenadas = criptos_filtradas.sort_values(by=['mean_roi_anual', 'market_cap'], ascending=[False, False])

# Mostrar las mejores 5 criptomonedas para invertir
mejores_criptos = criptos_ordenadas.head(5)

print(mejores_criptos[['name', 'mean_roi_anual', 'std_roi_anual', 'market_cap']])
```

Nota: Asegúrate de que las columnas `volumen_historico` y `capitalizacion_historica` estén en el mismo formato que el dataframe de precios antes de hacer este análisis.

Este es un enfoque muy básico y hay muchas otras métricas y factores que podrían ser considerados. Es importante hacer una investigación adicional y, si es posible, consultar con un asesor financiero antes de tomar decisiones de inversión.

El volumen promedio que has calculado para cada criptomoneda representa la cantidad media de esa criptomoneda que se ha negociado diariamente durante un período específico. Esta métrica es muy útil para entender la liquidez y la actividad de negociación de cada criptomoneda. Aquí te explico cómo interpretar estos números y qué podrías hacer con esta información:

**Interpretación del Volumen Promedio:**

1. **Bitcoin (14546.270584)**: Bitcoin tiene un alto volumen promedio de negociación. Esto indica que es una criptomoneda muy líquida, lo que es esperable ya que es la criptomoneda más conocida y ampliamente utilizada.
2. **Ethereum (9317.738785)**: Ethereum también tiene un alto volumen de negociación, lo que es coherente con su posición como la segunda criptomoneda más grande por capitalización de mercado.
3. **Tether (26533.345559)**: Tether, una criptomoneda estable (stablecoin), tiene el volumen promedio más alto en esta lista. Esto es común para las stablecoins, ya que se utilizan frecuentemente para mover dinero dentro y fuera del mercado de criptomonedas sin incurrir en la volatilidad asociada con otras criptomonedas.
4. **Criptomonedas con Volumen Promedio Bajo (como Staked-Ether y Dogecoin)**: Estas criptomonedas tienen un volumen promedio de negociación relativamente bajo, lo que podría indicar menor liquidez y, posiblemente, más dificultades para comprar o vender grandes cantidades sin afectar el precio.

**Utilización de esta Información:**

1. **Estrategia de Inversión**: Si eres un inversor, es posible que prefieras criptomonedas con un alto volumen de negociación, ya que estas monedas tienden a ser más líquidas y fáciles de comprar o vender.
2. **Evaluación de la Liquidez**: Si estás considerando invertir una suma significativa en una criptomoneda, querrás asegurarte de que la moneda tenga suficiente liquidez para permitirte entrar y salir de tu posición sin mover drásticamente el mercado.
3. **Identificación de Oportunidades de Trading**: Para los traders, especialmente aquellos que operan en plazos más cortos, la liquidez es crucial. Los traders a menudo buscan activos con alto volumen para minimizar el impacto de sus operaciones en el precio del activo.
4. **Evaluación de Riesgos**: Criptomonedas con bajos volúmenes de negociación pueden ser más volátiles y menos líquidas, lo que puede ser riesgoso si necesitas vender en un corto período de tiempo.
5. **Identificación de Anomalías**: Un cambio repentino en el volumen de negociación, ya sea un pico o una caída, podría ser una señal de que algo significativo está ocurriendo con esa criptomoneda.

Es importante recordar que el volumen promedio de negociación es solo una métrica. Siempre es esencial mirar una variedad de indicadores y realizar una investigación completa antes de tomar decisiones de inversión o trading. Además, los volúmenes de negociación pueden variar entre diferentes exchanges, por lo que es útil verificar múltiples fuentes.



Los KPIs (indicadores clave de rendimiento) te permiten medir la efectividad y el desempeño de distintas variables en relación a los objetivos establecidos. A partir de los datasets de criptomonedas que has mencionado, aquí hay algunas sugerencias de KPIs que podrías considerar:

1. **Rendimiento Total (ROI)** :

* Rendimiento anualizado.
* Rendimiento semestral, trimestral y mensual.

1. **Volatilidad** :

* Volatilidad anualizada (desviación estándar del rendimiento).
* Volatilidad semestral, trimestral y mensual.

1. **Capitalización de Mercado** :

* Cambio diario, semanal y mensual de la capitalización.
* Ranking de criptomonedas según su capitalización.

1. **Volumen de Transacción** :

* Volumen diario, semanal y mensual.
* Cambios en el volumen (porcentaje) respecto a períodos anteriores.

1. **Precios** :

* Precio más alto y más bajo durante un período determinado.
* Cambio en el precio (tanto en valor absoluto como en porcentaje) durante períodos específicos.

1. **Máximos y Mínimos Históricos (ATH y ATL)** :

* Número de veces que una criptomoneda alcanza su ATH o ATL durante un período específico.
* Porcentaje de cambio desde el ATH o ATL.

1. **Liquidez** :

* Relación entre volumen y capitalización de mercado.

1. **Dominancia en el Mercado** :

* Porcentaje de capitalización de mercado de una criptomoneda en particular en relación con la capitalización total del mercado de criptomonedas.

1. **Número de Transacciones** :

* Total de transacciones en un período específico.
* Cambio en el número de transacciones con respecto a períodos anteriores.

1. **Indicador de Salud del Mercado** :

* Relación entre volumen y volatilidad para identificar períodos de exuberancia irracional o pánico en el mercado.

Estos son solo algunos ejemplos y podrías desarrollar muchos otros KPIs según las necesidades específicas de tu análisis. Una vez definidos, puedes visualizar estos KPIs en herramientas como Power BI, Tableau, entre otras, para tener una visión clara y comprensible del comportamiento de las criptomonedas.
