# Classify-masses-as-Benign-or-Malignant
## Predicting whether a mammogram mass is benign or malignant

I used the "mammographic masses" public dataset from the UCI repository (source: https://archive.ics.uci.edu/ml/datasets/Mammographic+Mass)

This data contains 961 instances of masses detected in mammograms, and contains the following attributes:
   1. BI-RADS assessment: 1 to 5 (ordinal)  
   2. Age: patient's age in years (integer)
   3. Shape: mass shape: round=1 oval=2 lobular=3 irregular=4 (nominal)
   4. Margin: mass margin: circumscribed=1 microlobulated=2 obscured=3 ill-defined=4 spiculated=5 (nominal)
   5. Density: mass density high=1 iso=2 low=3 fat-containing=4 (ordinal)
   6. Severity: benign=0 or malignant=1 (binominal)
   
BI-RADS is an assesment of how confident the severity classification is; it is not a "predictive" attribute and I discarded it. The age, shape, margin, and density attributes are the features that I used to build the model with, and "severity" is the classification I attempted to predict based on those attributes.

Applied several different supervised machine learning techniques to this data set, and obtaibed the following accuracy as measured with K-Fold cross validation (K=10).
### 
Model  | Accuracy
------------- | -------------
Decision tree | 0.7373123154639465
Random forest | 0.7528157927878762
KNN(k = 10) | 0.7854795488574507
Naive Bayes | 0.7844055665169388
SVM Linear Kernel | 0.7964988875362076
SVM RBF Kernel | 0.8023928466479158 
SVM Sigmoid Kernel | 0.7374711389110449
SVM Poly Kernel | 0.793973454794789
Logistic Regression | 0.8073583532737221
Neural Network using Keras | 0.8060240983963013

The only clear loser is Decision Trees! Every other algorithm could be tuned to produce comparable results with 79-80% accuracy.
