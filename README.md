<p align=center><img src=imagenes/inversion.jpg>``<p>

<h1 align=center>**Analisis de Criptomonedas**</h1>

 Este repositorio es un proyecto individual cuyo objetivo es el analizis del mercado de las criptomonedas utlizando datos de la API [CoinGecko.](https://www.coingecko.com/es/api/documentation)

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
+ De [investing.com](https://es.investing.com/currencies/usd-ars-historical-data) obtuve el historial de 10 años del peso con respecto al dolar
+ Nulos. El tratamiento de los valores nulos rellenaron por interpolacion
+ Se calcularon indicadores de retorno de inversion, volatilidad y dominancia.
+ Se analizaron posibles relaciones entre las criptomonedas seleccionadas con una matriz de correlacion.
+ Se crearon datasets con la informacion de los indicadores y datosx relevantes de cada criptomoneda y de la evolucion del precio, el volumen y la capitalizacion.

Estas tareas se realizaron en una [Jupyter Notebook](https://github.com/smlopez30/analizis-del-mercado-de-las-criptomonedas/blob/main/analisis.ipynb) con VSS Code y se subieron a GitHub. Se utilizaron librerías como Pandas, Numpy, requests, Matplotlib.pyplot, datetime y statsmodels.tsa.seasonal.

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

- Creación de Dashboard Interactivo**

- Diseño e implementación de un dashboard interactivo utilizando una herramienta de visualización (Power BI).
- Inclusión de filtros que permitan a los usuarios explorar los datos de cada criptomoneda seleccionada.
- Representación visual clara y efectiva de los KPIs.

**Definición y Visualización de KPIs**

Los KPIs (indicadores clave de rendimiento) te permiten medir la efectividad y el desempeño de distintas variables en relación a los objetivos establecidos. A partir de los datasets de criptomonedas seleccionados, adetallo los KPIs considerados:

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

**Análisis y Recomendaciones**

- Insights:

Volatilidad: Las criptomonedas, en general, muestran una alta volatilidad en comparación con otros activos financieros tradicionales. Por ejemplo, Dogecoin y Ripple han mostrado volatilidades extremadamente altas en el pasado.

Dominancia: Bitcoin ha mantenido una dominancia significativa en el mercado de criptomonedas desde su inicio. Sin embargo, hemos observado que otras criptomonedas, como Ethereum, han ido ganando terreno en términos de capitalización de mercado.

Valores Anómalos: Hemos identificado valores anómalos en la dominancia de Ripple en ciertos puntos, lo que podría ser indicativo de eventos de mercado específicos o errores en los datos.

Lanzamientos: Las fechas de lanzamiento de las criptomonedas son cruciales. Algunas criptomonedas mostraron valores nulos después de su fecha de lanzamiento, lo que indica la falta de actividad o datos incompletos.

- Recomendaciones:

Diversificación: Dada la alta volatilidad de las criptomonedas, es recomendable diversificar las inversiones en varias monedas en lugar de concentrarse en una sola. Esto ayuda a mitigar el riesgo.

Monitoreo Continuo: Es esencial mantener un monitoreo constante del mercado, especialmente de las criptomonedas con alta volatilidad. Las alertas automáticas para cambios significativos en el precio o volumen pueden ser útiles.

Investigación Adicional: Antes de invertir, es crucial investigar eventos específicos que puedan haber causado picos de volatilidad o dominancia. Por ejemplo, el pico en la dominancia de Ripple en 2015 podría estar relacionado con un evento de mercado o un error en los datos.

Gestión del Riesgo: Establezca límites de pérdida para proteger su inversión. Dada la volatilidad del mercado de criptomonedas, es fácil incurrir en pérdidas significativas en un corto período.

Actualización de Datos: Asegúrese de que los datos que está utilizando para tomar decisiones estén actualizados y sean precisos. Hemos identificado algunos problemas con los datos, como valores nulos después de las fechas de lanzamiento, que deben abordarse.

Educación: Dado que el mercado de criptomonedas es relativamente nuevo y altamente técnico, es esencial educarse continuamente sobre las últimas tendencias, tecnologías y regulaciones.

- Estrategias de Monitoreo:

Herramientas de Análisis Técnico: Utilice herramientas de análisis técnico para identificar tendencias, resistencias y soportes. Estas herramientas pueden ayudar a predecir movimientos futuros del mercado.

Noticias y Eventos: Manténgase informado sobre las últimas noticias relacionadas con criptomonedas. Los eventos, como las regulaciones gubernamentales o los avances tecnológicos, pueden tener un impacto significativo en los precios.

Foros y Comunidades: Participe en foros y comunidades relacionadas con criptomonedas. Estos pueden ser lugares valiosos para obtener insights y opiniones de otros inversores y expertos en el campo.

En resumen, el mercado de criptomonedas ofrece oportunidades significativas de inversión, pero también viene con riesgos elevados. Una estrategia de inversión bien informada y una gestión de riesgos adecuada son esenciales para tener éxito en este mercado.

El principal atractivo que han tenido siempre, y que seguirán teniendo las criptomonedas, es que su potencial de ganancias es muy alto. Algunas de ellas, como es el caso del Bitcoin, han experimentado un aumento significativo en su valor. Esto ha generado muchas ganancias para los inversores que compraron bitcoin a precios bajos.

Sin embargo, es importante recordar que el valor de las criptomonedas así como sube también puede bajar. O sea que las ganancias no están garantizadas.

La volatilidad anualizada de varias criptomonedas, expresadas en términos porcentuales (es decir, multiplicadas por 100). En finanzas, la volatilidad es una medida común de riesgo y se usa ampliamente para comparar la estabilidad de diferentes activos. A continuación, te explico cómo interpretar estos números y qué podrías hacer a continuación con esta información:

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