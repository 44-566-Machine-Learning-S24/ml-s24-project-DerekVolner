# Conclusion
## Main Findings 
- Best metrics of any model came from the Random Forest in the Advanced Regression/Classification Tools at the bottom of this notebook: [Milestone 3](Milestone3.ipynb)
- The r2 of the linear regression model indicated a predictor that was weak due to having a number that was on the lower side of 1.0-0.0, that being 0.29 which can be found in the following link: [Link to Milestone 1: Linear regression Notebook](linear_regression.ipynb). 

## Narrative Story
- Side note not sure how this is supposed to differ between the conclusion in the readme and the the story following: 
- The model that was found that has the best metrics for the white wine dataset is the Random Forest and the reason as to why it is that the ensemble nature of the random forest might be taking our middle of the road performances, such as the decision tree giving us around 0.55 for accuracy and improving them.
- As for whether we can predict the quality of wine in the dataset my answer would be no because of a low r-squared value our predictions would be inaccurate as seen in the models in this repository
  - The reason why this might be the case is that perhaps we are missing an important input feature for the dataset such as like a recording for a select set of moods before someone did a sensory evaluation of the wine as listed in the study sensory evaluations are performed by people but there is no categorical or numerical data about the testers themselves, so if say a 1 was for a mood of someone who was "positive feeling" and a 0 for "negative feeling" we might be able to perform better predictions with this human aspect as an input feature.