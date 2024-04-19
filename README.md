# 44-566 machine-learning project
Repo for all project documents
## Links to Other sections:
- RAW_DATA
- DATA
- ANALYSIS
- CONCLUSIONS
## Introduction and Goals:
- My Project was using various models with the white wine dataset to discover various metrics(such as accuracy, f1-scores), vizualizations (such as the visualization of cluster's centroids), and find any relationships in the data. 
- Primary Goal:
  - See if with optimized input features in the dataset such as alcohol (alcohol percent by volume) or residual sugar (sugar left over from grapes after processing) or anything that contributes to predicting, if we can get a strong predictor of the output feature "quality".
- Secondary Goal:
  - Find the model which gives the best metrics back on the dataset such as with accuracy.


## Overview:
 I had in my original project proposal looked around and found to data sets from the government, but wasn't really satisfied with the data or subject that was in them.
- [First data set I looked at](https://www.census.gov/data/tables/2023/demo/income-poverty/p60-279.html)
- [ Second data set I looked at](https://www.census.gov/topics/families/marriage-and-divorce/data/tables.2022.List_1621025217.html#list-tab-List_1621025217)

I ended up searching around for a few hours today over various datasets from the UC Irvine Machine learning repo that was at the top of assignment 3, and narrowed it down to three:
- [WINE](https://archive.ics.uci.edu/dataset/186/wine+quality)
- [DROPOUT DATA](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)
- [AIR QUALITY](https://archive.ics.uci.edu/dataset/360/air+quality)

and ended up choosing **WINE** because the dataset wasn't too technical, and there wasn't any binary classifiers that were listed off on the webpage that I had to flip back and forth to look at. I specifically used the White wine csv

Then I performed looked at the data with some methods to get an idea of it, then used linear regression on the dataset to obtain r-squared, root mean squared, mean squared, bias, and coefficent metrics.
Overall I found that the data indicated low predictive power, with a good fit to the model.

### Notebook1: Initial Exploration:
I pulled in the dataframe, used hist() on it to get an idea of how the data in the features were distrubuted in by looking at the histograms, found correlations through corr(), got even more of an idea about the data through describe(), noticed I had no null data points, and found that through the scatter matrix that the closest thing to a linear correlation was between alcohol and density.

### Linear Regression:
I used the stratified split example from the files to perform a split on my data, then made working training set which was a copy of the training set that had been split from the original dataset, then I worked my way through with linear regression methods provided by sklearn to get my results. Modified the features used after the initial training set was ran to attempt to get better values on the metrics to see if I could improve them and I did.

## Important results:

#### Training Set-Post Improvements
- R^2^ value for the training set was:  0.2769342263179473
- Mean Squared Error was: 0.566878309113765
- Root Mean Square Error: 0.7529132148619554
  
#### Test Set
- R^2^ value for the testing set was: 0.293703737710699
- Mean Squared Error was: 0.5544469784101934
- Root Mean Square Error:  0.7446119649926353

## Important results from Project 2 Milestone:

### Notebook: Classification: 

#### Decision Tree findings
- Accuracy is  1.0 & F1 is  1.0
-  Cross validation accuracies are:  [0.576530612244898, 0.5471938775510204, 0.5625, 0.5530012771392082, 0.5606641123882503]
-  Cross validation f1 scores  are:  [0.5793953210504539, 0.5479319719338513, 0.5618041410237935, 0.5570180226934941, 0.5606869706999108]
- Basically every node only had one number indicating over fitting was occuring.

#### SVM Multi-classifier findings
- Accuracy is  0.5242470648289944 & F1 is  0.4441846223575155
- Cross validation accuracies are:  [0.4885204081632653, 0.5025510204081632, 0.4897959183673469, 0.5210727969348659, 0.46871008939974457]
- Cross validation f1 scores  are:  [0.4183026794633937, 0.42580947890174303, 0.42172918484473465, 0.4434337947004362, 0.380692231974421]
- This seems to me that we are no longer overfitting however we were getting missclassifications and the model was actually predicting,
- However it was doing it inaccurately and poorly which lines up with the low predictive power found by the R^2 in linear regression notebook.

## Important results from Project 3 Milestone:

### Notebook: Milestone 3:
#### Kmeans Clustering:
- The final distortion is: 9350.752692920545
- Centroids_x: 13.00322581 , 2.20665635 , 5.65348331 , 8.90639445 , 17.28817427 , 1.5861413, 65.8
- Centroids_y: 9.56736243 12.15500516 10.784388 10.15962506 9.34266943 10.2546558, 11.7
#### Dimensional Analysis:
- The number of dimensions that explain 95% of the variation:  2
#### Anomolous Data:
- ANOMALY FOR PCA: the x at: 1 has a corresponding y: at 0.93, means 1 feature explained 93% of the variance in the data.
- CLUSTERING ANOMALIES:
  - ANOMALY: the brown cluster of data points from the second graph in the previous part: has an x: 65.8
    - 65.8 is a massive outlier of the dataset being at about 3.5 times larger then the closest x value
### Advanced Regression/Classifier Tools:
#### Random Forest 
- Average cross validation accuracy for Random forest is: 0.64143654191
- Average cross validation f1-score for Random forest is: 0.62697622509
#### Neural Net
- Average cross validation accuracy for Neural Net 0.52110585923742792
- Average cross validation f1-score for Neural Net is: 0.469732875149119394



## Narrative	conclusion
- The model that was found that has the best metrics for the white wine dataset is the Random Forest and the reason as to why it is that the ensemble nature of the random forest might be taking our middle of the road performances, such as the decision tree giving us around 0.55 for accuracy and improving them.
- As for whether we can predict the quality of wine in the dataset my answer would be no because of a low r-squared value our predictions would be inaccurate as seen in the models in this repository
  - The reason why this might be the case is that perhaps we are missing an important input feature for the dataset such as like a recording for a select set of moods before someone did a sensory evaluation of the wine as listed in the study sensory evaluations are performed by people but there is no categorical or numerical data about the testers themselves, so if say a 1 was for a mood of someone who was "positive feeling" and a 0 for "negative feeling" we might be able to perform better predictions with this human aspect as an input feature.

