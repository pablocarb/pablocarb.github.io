---
layout: post
title:  "Modeling Covid-19 propagation"
date:   2020-03-29 16:34:22 +0100
categories: models
---

As we all struggle in this new uncharted situation of the Covid-19 pandemics around the world, most of us who work on modeling and engineering biology have been rushing to provide reliable information to figure out the extent of the outcome and to anticipate the next steps in order to curve down the damage.

I have been spending some time looking at ways for predicting the outcome assuming that

* There is an incubation period of 14 days;
* A SIR model can be fitted, taking into account the window of 14 days;
* Data is not always accurate and therefore we need to find the best time span from the published data and for each country;
* In addition, the model necessarily changes as countries take appropriate measures and therefore predictions might vary as countries put in place contention measures.

Based on such assumptions, there is a good fit between the models and the actual data. I have tried first to focus on South Korea, which is a country that has probably reached the peak thanks to their state measures.

![image](https://raw.githubusercontent.com/pablocarb/covid19/master/figs/Korea%2C%20South-2020-03-29-17-56-44.png)

In the plot, we can see how the reported cases in the incubation window fit to a model which approximately follows the actual values. The total reported cases are also shown for reference.

In Italy, the most accurate model is at the moment controversial due to a latest increase in cases. Therefore, it would be necessary to follow up with the reports in the next days in order to get a clear picture.

![image](https://raw.githubusercontent.com/pablocarb/covid19/master/figs/Italy-2020-03-29-17-58-44.png)

In France, the model seems to be quite accurate and assumes a peak around April 4th.

![image](https://raw.githubusercontent.com/pablocarb/covid19/master/figs/France-2020-03-29-17-58-13.png)

In Spain, the model has a good fitting, expecting the peak around April 2nd.

![image](https://raw.githubusercontent.com/pablocarb/covid19/master/figs/Spain-2020-03-29-17-55-51.png)

The code can be found [here](https://github.com/pablocarb/covid19). An updated notebook will be soon available.
