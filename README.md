# Assessing-the-Quality-of-Wine
A 7-class classification problem of wine classification based on various physical and chemical attributes of wine.

Language: R
IDE used: RStudio

Linear models used: 
1) LDA 
2) KNN

Non-Linear models used: 
1) SVM 
2) Decision Tree 
3) Random Forests (a Bagging algo)

Resampling Technique for Linear models used: 
1)Bootstrap

DATASET: 
The dataset was downloaded from the UCI Machine Learning Repository. 
The quality is measured in terms of integers ranging from one to ten, the more the integer value, the better-quality wine.
The dataset consists of 4898 rows and 12 columns.
The different values in the quality column in our dataset include 3, 4, 5, 6, 7, 8 and 9. Hence, we apply different 7-class classification models on our dataset.

DETAILS OF DATA PRE-PROCESSING:
1. For running the non-linear models on  RStudio, the y column had to be changed to categorical type. Meaning, it consisted of integer values of 3,4,5,6,7,8 and 9 originally. 
   It had   to be changed to three, four, five, six, seven, eight and nine.  
2. For the purpose of ease of work, I also included an extra column of serial number which served as an index to each data point.

ACCURACY FOR DATA MODELS:
1) LDA: 52.5% 
2) KNN: 52.9% [Parameter value assigned: K = 70]
3) SVM: 52.5% [Parameter value assigned: gamma=0.1, cost=10]
4) Decision Trees: 47.63% [Parameter value assigned: minsplit=1000; mincriterion:0.95]
5) Random Forest: 58.62% [Parameter value assigned: No. of trees=500, No. of valriables tried at each split=3]

AOC for ROC curve (calculated for Random Forest): 0.79

ANALYSIS:
1. Overall, we see that the non-linear models fit better than the linear models on our data.
2. Specifically, Random forest should act better than any other model specified because here, it has the maximum accuracy of 58.62%. 
3. We perform bootstrap aggregation in Random Forests to increase prediction accuracy.
4. So, as we build separate prediction models using each training set made from the original training dataset and then average out the resulting prediction, the results are good.
5. It also overcomes the problem of a very strong predictor shadowing the effects of other predictors by forcing each split to consider only a subset of predictors. 
