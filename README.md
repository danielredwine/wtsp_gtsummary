---
title: "White-throated Sparrow Juvenile and Adult Feathers"
author: "Daniel Redwine"
date: "`r Sys.Date()`"
output: 
  html_document:
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(fig.asp = .66, fig.width = 5)
#Its common to have a setup area to help keep track of required packages and formatting options

library(tidyverse)  #importing, tidying, plotting data
library(knitr)      #making tables
library(leaflet)
library(dplyr)
library(hexbin)
library(ggplot2)
library(readr)
library(RColorBrewer)
library(ggfortify)
library(emmeans)
library(multcomp)
library(multcompView)
library(tidyr)
library(gridExtra)

#knitr::opts_chunk$set(fig.width = 5, fig.asp = 1/3) #force figures to be a certain size and aspect ratio
#opts_chunk$set(echo=FALSE)   #can force hide all code in the output; disables 'code folding'
```
# White-Throated Sparrows Feathers

Traditionally juvenile birds grow all their feathers in the nest over a short time period while adult birds incrementally molt their feathers over a longer time period. Therefore, there may be different energetic demands which mediate differences in composition of feathers between adult and juvenile birds. White-throated Sparrows are a polymorphic species, so there may also be differences between sex and morph. Here we perform a t-test, two-way ANOVA, and ANCOVA to investigate differences between adult and juvenile White-throated Sparrows. More information on White-throated Sparrows can be found [here](https://www.allaboutbirds.org/guide/White-throated_Sparrow/overview).

```{r wtsp morphs, echo=FALSE, fig.show = "hold", out.width = "50%", fig.align = "default", fig.cap="Figure 1.Presumed white morph (left) and tan morph (right) White-throated Sparrows"}
## echo=FALSE ensures that the code does not show in the final knit product
## out.width is for width of the figures, fig.align default places them next to eachother
## fig.cap adds a caption to the figure

knitr::include_graphics("images/White_morph.png") ## To include the first figure
knitr::include_graphics("images/tan_morph.png") ## To include the second figure


```