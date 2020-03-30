---
layout: post
title:  "Covid-19 model details"
date:   2020-03-30 12:34:22 +0100
categories: models
author: Pablo Carbonell
---

# The SIR model

The dynamics of the COVID-19 will be modelled using the SIR model:

$\frac{dS(t)}{dt}  =   - \beta \frac{I(t) S(t)}{N}$

$\frac{dI(t)}{dt} =  \beta I(t) \frac{I(t) S(t)}{N} - \gamma I(t) $

$\frac{dR(t)}{dt}  =  \gamma I(t)$

where $S(t)$ is the stock of susceptible population, $I(t)$ is the stock of infected, $R(t)$ is the stock of recovered population, and $N$ is the sum of these three.

 - $\beta$ is the average number of contacts per person per time;
 - $\gamma$ is the rate of recovered;
 - $R_0 = \frac{\beta}{\gamma}$ is the basic reproduction number.

# The discrete SIR model

The previous equations for the SIR model will be approximated using the following difference equation:

$S_{t+1} = S_t - T \beta S_t \frac{I_t}{N}$

$I_{t+1} = I_t + T \beta S_t \frac{I_t}{N} - T \gamma I_t$

$R_{t+1} = R_t + T \gamma I_t$

where $S_t$ are the susceptible population, $I_t$ is the infected and $R_t$ the recovered. $T$ is the sampling period, typically 1 day.

# Model and data estimation

In order to estimate the parameters of the model $(\hat \beta, \hat \gamma)$, we will use an optimizer that will minimize the root mean square difference between the predicted infected population $I_t$ and the actual infected retrieved from official data daily published by the John Hopkins University.

The data contains three time series, i.e., reported ($P_t$), recoveries ($C_t$) and deaths ($D_t$). We will assume an incubation period of $i = 14$ days. The actual infected $I_t^*$ will be estimated by looking at the increase in reported cases for the incubation period less recoveries and deaths:

$I_t^* =   P_t - C_t - D_t - P_{t-i}$

## Acknowledgements

Thanks to [lewuathe](https://www.lewuathe.com/covid-19-dynamics-with-sir-model.html) for coding templates.
Thanks to [MUNQ](https://covid19.webs.upv.es/) for initial ideas.
