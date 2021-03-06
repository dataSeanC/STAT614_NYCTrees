# STAT614_NYCTrees
Repo for our NYC Trees Project

* [Interpret Logistic Regression](https://stats.idre.ucla.edu/other/mult-pkg/faq/general/faq-how-do-i-interpret-odds-ratios-in-logistic-regression/)
* [Interpret Multinomial Logistic Regression](https://stats.idre.ucla.edu/stata/output/multinomial-logistic-regression-2/)

## Logistic Regression
```{r}
# Here's a general linear model, logisitc regression for R:
log.fit <- glm(y ~., family = binomial(link=logit), data = train)
```

## STEPWISE VARIABLE SELECTION
```{r}
# Choose the best model via the stepwise procedure:
null = glm(y ~ 1, family = binomial(link=logit), data = train)
full <- glm(y ~., family = binomial(link=logit), data = train)
step(null, scope=list(lower=null, upper=full), direction="both")
# This will output the reduced model. That's the one we use. We do this for both groups.
```

* Data Source [https://data.cityofnewyork.us/Environment/2015-Street-Tree-Census-Tree-Data/pi5s-9p35]
* Data Dictionary [https://data.cityofnewyork.us/api/views/pi5s-9p35/files/2e1e0292-20b4-4678-bea5-6936180074b3?download=true&filename=StreetTreeCensus2015TreesDataDictionary20161102.pdf]
