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
   
### Variable Exploration
   
For most variables, we will study the skewness, the kurtosis and we will show some visuaal representations in order to know better the dataset.

## Weeks Column

   + skewness = 0.82 : it is moderately skewed
   + kurtosis = 0.21 : close to 0, therefore we could assume that this variable has a distribution close to a normal one.

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/weeks1.PNG)
![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/weeks2.PNG)

From the graph the 10 outliers seem to be abover the upper whisker:

![picture](https://github.com/pberjon/OSIC-Pulmonary-Fibrosis-Progression-Competition/blob/main/images/tab2.PNG)


