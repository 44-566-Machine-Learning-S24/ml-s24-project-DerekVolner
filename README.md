# 44-566 machine-learning project
Repo for all project documents


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

