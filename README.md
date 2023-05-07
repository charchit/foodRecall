# foodRecall <a href="https://loganjohnson0.github.io/foodRecall/"><img src="man/figures/hex-foodRecall.png" align="right" height="150" style="float:right; height:150px;" /></a>

  <!-- badges: start -->
  [![R-CMD-check](https://github.com/loganjohnson0/foodRecall/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/loganjohnson0/foodRecall/actions/workflows/R-CMD-check.yaml)
  <!-- badges: end -->

## Introduction
To use this package, it is necessary that you register for an API key through the [openFDA website](https://open.fda.gov/apis/authentication/). This is a free API key that only requires your email address. You should receive it immediately upon request. Upon any issues with the API key itself, please contact the openFDA office. Be sure to not share your API key with anyone!

## Installation

```{r}
# install.packages("devtools")
library(devtools)

devtools::install.github("loganjohnson0/foodRecall")

library(foodRecall)
```

To use the `foodRecall` package, you will need to enter your API key into the `get_fda` function. You will also need to define the number of requests that you would like to request. The limit is 1000 so if you enter a number larger than 1000, an error will occur. (Working on adding in that limitation in the package itself). 

```{r}
df <- foodRecall::recall_location(api_key = "YOUR API KEY", 
                                  limit = "NUMBER OF RECALL EVENTS")
```

We also are working on visualizing these data on a location basis. We are working on adding in additional capabilities, such as the scale of the product recall and other interactive capabilities. It is best to not change the column headers from those in the generated `get_fda` function.

```{r}
foodRecall::map_recall(data = df)
```
Here is an example output of the type of map that would be generated.

![Rplot.pdf](Rplot.pdf)


Check back for additional updates that we plan to add in soon!

# This product uses the openFDA API but is not endorsed or certified by the Food and Drug Administration.

