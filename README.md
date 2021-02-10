# OSIC-Pulmonary-Fibrosis-Progression-Competition

This is a proposition of solution for the OSIC Pulmonary Fibrosis Progression Kaggle Competition.

The aim of this work is to study the impact of the smoking status over the pulmonary functions.

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/tab1.PNG)

In that dataset, we have 7 different variables :

   + Patient- a unique Id for each patient (also the name of the patient's DICOM folder)
   + Weeks- the relative number of weeks pre/post the baseline CT (may be negative)
   + FVC - the recorded lung capacity in ml
   + Percent- a computed field which approximates the patient's FVC as a percent of the typical FVC for a person of similar characteristics
   + Age
   + Sex
   + SmokingStatus
   
For most variables, we will study the skewness, the kurtosis and we will show some visuaal representations in order to know better the dataset.

## Target : SmokingStatus Column

Here we can see the distribution of SmokingStatus(pie) : 

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/pie.PNG)

The lack of information concerning people who are currently smoking will be a problem in that work, because we won't be able to clearly see the influence smoking has on pulmonary functions (even if ex-smokers will give us some good information).

## Weeks Column

   + skewness = 0.82 : it is moderately skewed
   + kurtosis = 0.21 : close to 0, therefore we could assume that this variable has a distribution close to a normal one.

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/weeks1.PNG)
![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/weeks2.PNG)

From the graph the 10 outliers seem to be abover the upper whisker:

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/tab2.PNG)

## FVC Column

   + skewness = 0.58
   + kurtosis = 0.57
   
![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/fvc1.PNG)
![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/fvc2.PNG)

We decide to only to show the 5 first outliers :

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/tab3.PNG)

Understanding the relationship bwtween 2 variables :

   + Bivariate analysis
   + Multivariate analysis

## Bivariate analysis

Let's understand the trend between two variables.

Firstly, we have to point out the fact that a normal percent (for a healthy person) has to be between 80% and 120%.

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/lineplot1.PNG)
![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/heatmap1.PNG)

There is a high positive correlation between Percent and FVC.

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/lineplot2.PNG)
![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/swarmplot1.PNG)

With swarmplot we can clearly identify the consequences of smoking on percent (ex-smoker or currently smoking person).

## Multivariate analysis

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/scatterplot1.PNG)

Our dataset "currently smokes" is quite small, but we can see that smoking is really dangerous for old people beacuse their percent is way too high (> 140%). For ex-smokers, it's more complicated, but it's visible (too low or too high).

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/scatterplot2.PNG)

## Model fitting

Here, we'll choose a Logisitc Regression model (because we do a classification task).

It's confusion matrix is right below : 

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/cm1.PNG)

With this model, we have 71% of accuracy.

Here we train our data with a Random Forest Classifier : 

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/cm2.PNG)

With this one, we got 79% of accuracy.
