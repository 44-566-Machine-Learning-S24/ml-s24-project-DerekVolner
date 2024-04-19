### Exploration of the Data
- No null data points existed in the dataset
- Found that through the scatter matrix that the closest thing to a linear correlation was between alcohol and density.
- Found that there existed a negative correlation between the residual sugar and the quality of the data.
- Also found through working with the scatter matrix that most of the data did not have linear correlations with some being almost a mass of circlular data instances showing close to now correlation.
- Most of the data fit into a normal distribution, whether that be left or right skewed however the data for residual sugar appears to have a major issue with most values being at left ended in a very narrow margin.
- Found through k means clustering that a cluster of the data is centeroid abnormally far to the right on the x-axis about at 60 which is about 3.5 times greater x value than any other centroid.
- Found that residual sugar explained about 93 percent of the variation in the data, despite not having the most effect whenever I was altering the input features being tested during the [Linear Regression](linear_regression.ipynb) part of the project.
  - it still mattered to the r^2 value but not to the degree I would expect from both this finding and the fact it was correlated with the quality in the initial exploration
  - I went back because it's been a long time since we worked on the linear regression and did some testing on the [Linear Regression](linear_regression.ipynb) and in order the ones that effected the r^2 the value the most when taking them out of the input features on the test set on the last code cell were: Volatile Acidity, Alcohol, and Residual Sugar, I would still expect Residual sugar to be have more effect on the change due to the previous 93 percent explantion of variance and the correlation with quality. 


### Transformations
- I was having trouble enforcing a standard scaler on the data, and the only other "transformation on the dataset" that might have been applied would have been doing stratifications on the splits which you can see at the top of the following notebook:
  - Stratification occurs in the first cell here: 
  - [Stratified](classification.ipynb)
### Notebooks that contain Vizualations of the Data in any manner:
- [Start of Exploration](initial_exploration.ipynb)
 - Histogram and a scatter matrix are vizualized here.
- [Kmeans and PCA Vizualizations](Milestone3.ipynb)
  - Vizualizations are on the 4th heading in the above titled: Vizualization and Narrative Data Predictively