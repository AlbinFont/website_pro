+++
title = "Estimation of an arbovirus incubation period distribution based on travellers data: A Star Wars example"

date = 2018-12-05T00:00:00
# lastmod = 2018-09-09T00:00:00

draft = false  # Is this a draft? true/false
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.

# Add menu entry to sidebar.
linktitle = "Estimation of an arbovirus incubation period distribution"
[menu.tutorial]
  parent = "Tutorials"
  weight = 1
+++

We will see here how to estimate an incubation period distribution in humans for a vector-borne pathogen. Incubation period (IP) is defined as the time elapsed from virus acquisition to onset of symptoms in humans. Estimating the duration of IP in humans is not straightforward for vector-borne diseases because date of infection through the bite of an infectious vector cannot usually be determined. We will exploit here declared travel and symptom dates of travelers entering or leaving areas with ongoing virus transmission.
This code was used for the paper "Variability of Zika Virus Incubation Period in Humans" (https://www.ncbi.nlm.nih.gov/pubmed/30397624). For data confidentiality purpose, we are going to use here a fake dataset.


## Load packages

```{r, packages, results='hide', fig.height=4}
library(survival)
library(plyr)
library(ggplot2)
library(lubridate)
library(interval)
library(icenReg)
library(survminer)

```

## Load data set
```{r, chunk-label, fig.height=4}

data <- read.table(file = "Data_IP_fake.txt", h=T)
head(data)
```
