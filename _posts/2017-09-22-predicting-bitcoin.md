---
title: 'Cases in Analytics'
layout: post
date: '2017-10-22'
permalink: /es/blog/analytics-cases/
published: false
share-img: "/img/posts/portaldatos/opendata_graph_PC.png"
bigimg: "/img/posts/portaldatos/opendata_graph_PC.png"
tags:
- English
- Analytics
- Data Science
- Visualization
- Sentiment Analysis
- Clustering
- Web Scraping
- Dashboards
---

# Bitcoin

## Situation

We wanted to figure out how to predict the Bitcoin price to see if we could find some hidden patterns out of the data. 

## What we did

We test several machine learning models to estimate the price. We connected to a real time Bitcoin data source and choose 26 different models 

## Benefit

Bla, bla, bla.

## Why me

Bla, bla, bla.

## Technical highlights

Bla, bla, bla.



```{r}
install.packages(c("quadprog", "xts", "TTR", "quantmod"), dependencies = TRUE)
require(quantmod)
getSymbols("BTC/USD",src="oanda")
barChart(BTCUSD)
chartSeries(to.weekly(BTCUSD))
addMACD()
addBBands()

```


En el [archivo de Excel](/files/Datos.xlsx) hay información de precios desde el 10 de Abril de 2013 al 26 de Mayo de 2017 de la empresa "XYZ". Me dí a la tarea de desarrollar un modelo estadístico que pronosticara si el precio de una acción sube o baja en función de su valor histórico y otras variables. Este análisis fue desarrollado en R, Markdown y GitHub y es hecho con propósitos investigativos. El código fuente pueden hallarlo en mi [reposotorio (carpeta)](https://github.com/cecabrera/stock) en GitHub.

El plan de trabajo de este informe se resume en:

1. análisis de Regresión Logística para encontrar asociaciones entre los indicadores y el precio de la acción;
2. análisis de ARIMAX para modelar el comportamiento de los retornos y calcular la tendencia y magnitud del precio en el corto plazo; 
3. y finalmente una sucesión de códigos en GitHub para evaluar 25 modelos estadísticos en un bucle y determinar cuál tiene la mejor precisión al momento de pronosticar el precio de la acción. 

Comenzamos cargando los paquetes a utilizar y los datos del archivo de Excel:

```{r}

require(caTools)
require(tseries)
require(readxl)
require(data.table)
require(ggplot2)
require(corrplot)
library(ROCR)

d <- data.table(readxl::read_excel(path = "Datos.xlsx", sheet = 1))

head(d[, .(fecha, open, high, low, close, volume)])
```

En la hoja `campos` del archivo de Excel se encuentra la descripción de cada una de las columnas de la variable `d`.

Graficamos el precio de cierre usando la librería `ggplot2`:
```{r}

ggplot(data = d, aes(x = fecha, y = close)) + geom_line()

```

Antes de proceder a modelar los datos, los vamos a dividir en dos: un bloque de "training" para entrenar el modelo con el 80% de los datos y un bloque de "testing" para calcular el nivel de precisión de nuestro modelo con los datos más recientes. 

```{r}
train <- d[1:floor(nrow(d)*0.8),]
test <- d[(floor(nrow(d)*0.8)+1):nrow(d)]
```

## Modelo de regresión logística

Todas las variables en el archivo de Excel (a excepción de `fecha`) son numéricas. Mediante un modelo de regresión logística múltiple (Logit), calculamos las variables con mayor incidencia en la explicación de la variable `close_trend`.

```{r}
model <- glm(close_trend ~ ., family = binomial(link = 'logit'), data = train[, -1, with = FALSE])
summary(model)
```

Estadísticamente, las variables que 'explican' el comportamiento de `close_trend` son:

- El intercepto del modelo.
- [`high`]: representa el punto más alto que alcanzó la acción en determinado día.
- [`p_bollinger_lower_band`](https://es.wikipedia.org/wiki/Bandas_de_Bollinger): son bandas de volatilidad que se ubican por encima y por debajo de una media móvil. 
- [`p_average_true_range`](http://stockcharts.com/school/doku.php?id=chart_school:technical_indicators:average_true_range_atr): es un indicador que mide _volatilidad_. Según el modelo, por cada unidad que aumenta el logaritmo de esta variable (porque es un modelo Logit), el logaritmo del precio de cierre aumenta en 3.765 unidades.
- `p_average_true_range_v3`: radio del `p_average_true_range/cierre`.
- [`p_detrended_price_oscillator`](http://stockcharts.com/school/doku.php?id=chart_school:technical_indicators:detrended_price_osci): indicador diseñado para remover la tendencia de los precios y hacer más fácil la identificación de ciclos.
- [`p_know_sure_thing`](http://stockcharts.com/school/doku.php?id=chart_school:technical_indicators:know_sure_thing_kst): indicador que mide el _momentum_ del precio para cuatro diferentes ciclos de precios.

Todas estas variables fueron construidas basadas en el precio histórico; lo que compromete la calidad del modelo al violar el supuesto de no-multicolinealidad.

Mientras que no hay un equivalente al `R²` de los modelos de regresión lineal, el `R²` de McFadden puede ser usado para calcular el ajuste del modelo. 

```{r, message=FALSE, warning=FALSE}
require(pscl)
pR2(model)["McFadden"]
```

## Calculando la habilidad predictiva del modelo

Es momento de calcular la precisión del modelo utilizando los datos de la variable `test` definida previamente. En vista que es un modelo Logit, el output son probabilidades por lo que usaremos una cota de 0.5 para determinar si el precio sube o bajo en los próximos días.

```{r, message = FALSE, warning=FALSE}
fitted.results <- predict(model,newdata=test[, c(-1, -7), with = FALSE],type='response')
fitted.results <- ifelse(fitted.results > 0.5, 1, 0) # Cota de 50%
misClasificError <- mean(fitted.results != test$close_trend)
print(paste0('Precisión: ',round(100*(1-misClasificError), 1), "%"))
```

Una precisión del `64.9%` es relativamente baja. Hay que tomar en consideración que factores como escoger 80% de los datos y no otra cifra influye en el cálculo de los coeficientes y p.e. en la precisión del modelo. A su vez, es útil en este punto utilizar métodos de cross validación como k-fold u otros disponibles para iterar con las combinaciones de variables y parámetros que resulten en un mejor modelo.

Como último paso, calcularemos la _curva ROC_ y el área bajo la curva (AUC) las cuales son medidas típicas de desempeño para clasificadores binarios. 

El ROC es una curva creada para graficar la tasa de verdaderos positivos contra los falsos positivos en varias configuraciones, mientras que el AUC es el área bajo la curva de ROC. Como estándar en la academia, un modelo con buena habilidad predictiva debería estar cercano a 1 y lejos de 0.5 en el coeficiente de AUC.

```{r, message = FALSE, warning=FALSE}
p <- predict(model,newdata=test[, c(-1, -7), with = FALSE],type='response')
pr <- prediction(p, test$close_trend)
prf <- performance(pr, measure = "tpr", x.measure = "fpr")
plot(prf)

auc <- performance(pr, measure = "auc")
auc <- auc@y.values[[1]]
auc
```

## Análisis con modelos ARIMAX

```{r, message=FALSE, warning=FALSE}
d$returns <- c(NA, diff(d$open, lag = 1))

print(adf.test(d$close))
# Por resultado del Augmented Dickey-Fuller Test la serie no es estacional. A stationary time series means a time series without trend, one having a constant mean and variance over time, which makes it easy for predicting values.

logical <- !is.na(d$returns)
print(adf.test(d[logical, returns]))
qplot(y = returns, x = fecha, geom = "line", data = d[logical])
# Ya es estacional por el p-valor inferior a cero.
rm(logical)
 
set.seed(101) 
sample = sample.split(d$returns, SplitRatio = .80)
train = subset(d$returns, sample == TRUE)
test  = subset(d$returns, sample == FALSE)
 
```

Fuente de información: https://www.r-bloggers.com/forecasting-stock-returns-using-arima-model/

## Análisis iterativo de 25 modelos

Código fuente: https://github.com/daumann/r-stockPrediction/blob/master/findBestPrediction.r

En el ejemplo de este código, de los 25 modelos intentados, el óptimo fue uno de Redes Neuronales Artificiales. 

# Conclusiones

En la teoría, las variables del modelo de Regresión Logística 'explicaron' parte del comportamiento del precio de la acción. En la práctica, __los precios de las acciones responden a las expectativas que tiene el mercado en función de nueva información (como noticias)__ y por ende, ninguna de las demás variables en la base de datos entran en esta categoría: dependen de información pasada. Hay que tener prudencia cuando se tomen decisiones de inversión teniendo en cuenta _únicamente_ estas variables. 

Por otro lado, la estructuración de modelos de series de tiempo aglutinan toda información pasada y están diseñados para considerar tendencias, eventos pasados y lags entre eventos. Es por esta razón que un modelo autorregresivo (AR) integrado (I) de media móvil (MA) desempeña un mejor papel teórico en la modelación del precio de las acciones. Aún así, hay que considerar variables como noticias y tendencias en redes sociales para tener un mirada holística de lo que sucede con la acción. 

Finalmente, la precisión de un modelo está atada a su desempeño frente al "test" dataset y de sus métricas respecto a otros modelos. De ahí la importancia de cross validar con varias opciones.

# Fuentes bibliográficas

- https://www.quantinsti.com/blog/forecasting-stock-returns-using-arima-model/
- https://github.com/daumann/r-stockPrediction
- http://colorado.rstudio.com:3939/commodities-quandl-flexdb/
- http://www.sthda.com/english/wiki/correlation-matrix-a-quick-start-guide-to-analyze-format-and-visualize-a-correlation-matrix-using-r-software
- https://www.r-bloggers.com/how-to-perform-a-logistic-regression-in-r/
- http://www.statisticssolutions.com/assumptions-of-logistic-regression/
