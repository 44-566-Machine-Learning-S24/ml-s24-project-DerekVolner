### Linear Regression:
-[Link to Milestone 1: Linear regression Notebook](linear_regression.ipynb)
I used the stratified split example from the files to perform a split on my data, then made working training set which was a copy of the training set that had been split from the original dataset, then I worked my way through with linear regression methods provided by sklearn to get my results. Modified the features used after the initial training set was ran to attempt to get better values on the metrics to see if I could improve them and I did.

## Important results:

#### Test Set
- R^2^ value for the testing set was: 0.293703737710699
- Mean Squared Error was: 0.5544469784101934
- Root Mean Square Error:  0.7446119649926353

### Tuning the model
- What worked:  
  - testing input features so that we got a higher r-squared value and RMSE values, which included removing features like Total Sulfur dioxide and replacing them with features such as residual sugar
- What didn't work: 
  - I couldn't get above a 0.29 on the training set so attempting to get a strong predictor from the input features available in the dataset was not achieved.

### Challenges and Limitations
- A challenge of getting this to perform well is that it wasn't obvious to me at first which input features were going to give back the best metrics, so I had to do multiple different variations until I landed on a group of features that got me 0.29 on the testing set.
- A limitation of this specific part is that most the data from the exploration part of the project appeared to not be linearly correlated with quality or other features making it hard to predict with the Linear model.

### Improvements that could be made
- Utilizing a standard scaler might improve the data, and other transformation techniques
- Graph the linear regression model to see if potentially there is any way we could manipulate the model to fit the data better or if as I suspect non-linearly correlated data would be more sufficient.

## Important results from Project 2 Milestone:

### Notebook: Classification: 
-[Link to Milestone 2: Classification Notebook](classification.ipynb)

#### Decision Tree findings
- Accuracy is  1.0 & F1 is  1.0
-  Cross validation accuracies are: [0.576530612244898, 0.5471938775510204, 0.5625, 0.5530012771392082, 0.5606641123882503]
-  Cross validation f1 scores are: [0.5793953210504539, 0.5479319719338513, 0.5618041410237935, 0.5570180226934941, 0.5606869706999108]
- Basically, every node only had one number indicating over fitting was occurring.

#### SVM Multi-classifier findings
- Accuracy is  0.5242470648289944 & F1 is  0.4441846223575155
- Cross validation accuracies are: [0.4885204081632653, 0.5025510204081632, 0.4897959183673469, 0.5210727969348659, 0.46871008939974457]
- Cross validation f1 scores are: [0.4183026794633937, 0.42580947890174303, 0.42172918484473465, 0.4434337947004362, 0.380692231974421]
- This seems to me that we are no longer overfitting however we were getting misclassifications and the model is making predictions.
- However, it was doing it inaccurately and poorly which lines up with the low predictive power found by the R^2 in linear regression notebook.


### Tuning the models
- What worked: 
  - For the support vector machines I had tested multiple kernels and the one that actually did the best was the linear kernel to my surprise, as for the Decision Tree model I did not really tune the model.
- What didn't work: 
  - When testing the SVM kernels my polynomial, rbf, and sigmoid did worse than the linear kernel.

### Challenges and Limitations
- One challenge right out of the gate when doing this part of the project was attempting to see which kernel was going to do the best because I couldn't make heads or tails of as to why linear kernel was outperforming the others and thought I was doing something wrong so I redid the program for the same results.
- A limitation on this aspect of the project was that increasing instances past about 10,000 instances results in the SVM running incredibly slow and with the current model SVM's were still taking a while to run and might not have reached convergence.

### Improvements that could be made
- One improvement that could be made is turning the training instances to let the SVM run longer so that it's metrics might improve, or Using something like PCA to aid in dimension reduction.

## Important results from Project 3 Milestone:

### Notebook: Milestone 3:
-[Milestone 3 Notebook](Milestone3.ipynb)
#### Kmeans Clustering:
- The final distortion is: 9350.752692920545
- Centroids_x: 13.00322581 , 2.20665635 , 5.65348331 , 8.90639445 , 17.28817427 , 1.5861413, 65.8
- Centroids_y: 9.56736243 12.15500516 10.784388 10.15962506 9.34266943 10.2546558, 11.7
#### Dimensional Analysis:
- The number of dimensions that explain 95% of the variation:  2
#### Anomalous Data:
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

### Tuning the models
- What worked: 
  - Tuning the neural net with more instances increased the metrics, even though it took longer, as well as changing it from 1e-4 to 1e-5. The random forest didn't need any real tuning calling it with default settings gave the best performance out of ever model, with the next closest being A decision Tree, then neural net, then svm.
- What didn't work: 
  - Despite adding more instances to the neural net its improvement was only marginal, alongside this I got weird issues when attempting to run PCA and do the dimensional analysis the Standard scaler kept giving me issues I was not able to resolve by submission time.

### Challenges and Limitations
- One challenge was attempting to figure out an optimal configuration for the Neural net as increasing instances seemed to give varying level of improvements and I had to cut off the amount past as certain point because it was to long for what I was getting out of the model in comparison the Random Forest.
- One limitation of this that happened due to errors was getting issues with Standard Scaler, and the second limitation was having a personal knowledge limitation on potentially if there was a better solver or other parameters to get the neural net to perform better on the metrics with my data.

### Improvements that could be made

- Instead of using a standard neural net here I could test how a convolutional neural networks with the data and see if the neural net potentially running into exploding gradients or vanishing gradients would improve the results. Essentially a model change for the neural net seems like a way forwards to a potential improvement.