# July 21st, 2020 Lecture Response
## Premade Estimators
1. We used the .pop function to remove the "species" column, which was the target. The feature columns are the lengths and widths of the sepals and petals of the flowers.

2. Fives estimators derived from tf.estimator.Estimator are:

- tf.estimator.DNNEstimator() 
    - for Deep Neural Network models with user-specified head
- tf.estimator.BoostedTreesEstimator() 
    - which uses sequential decision trees
- tf.estimator.BaselineEstimator() 
    - which predicts the average value of each label
- tf.estimator.DNNLinearCombinedEstimator() 
    - for Linear and DNN joined models with custom heads
- tf.estimator.LinearEstimator 
    - for linear models with custom head

The above estimators also has "classifier" variants.

3. An input function is how we supply our data and labels to our model. The function creates a dictionary containing our feature values keyed by the feature name and an array of labels. The input function streamlines Defining a feature column allows us to describe how we want our data to enter our model. We could input our features (or a subset of them) into our model unchanged, or we could transform them by splitting a feature into a set of buckets, splitting a column into binary labels indicating a class (to remove any bias from the order of the numberical labels), etc. 

4. "Classifier" is a DNNEstimator, which is designed to produce a deep neural network which is designed to predict classifications rather than a continous regression. Our four layered model (feature layer, two hidden layers, and 3 neuron output layer) is trained by entering data through our input function. In our input function, we shuffle our dataset each iteration. We stop training the model after 5000 steps.

5. Accuracies of various Estimators on Iris Dataset

- LinearClassifier: 0.967
- DNNLinearCombinedClassifier: 0.933
- DNNestimator: 0.833

---
## Linear Model

![16](/DATA310_Images/21_0.png)
![16](/DATA310_Images/21_1.png)

1. The Seaborn plot of age appears to be a squished version of the histogram. We can tell from the histogram that most passengers were in their 20s and 30s. There were also a large number of people in their 40s and around 25 very young children.

2. A dense feature column is merely the features listed within a single column, while a categorical column has as many subcolumns as there are categories for that feature that contain binary values denoting if a given observation belongs to a given category.

![16](/DATA310_Images/21_2.png)
![16](/DATA310_Images/21_3.png)

3. For the linear classifier, we input age and fare as dense feature columns and all other features as categorical columns. The linear model reached around 76% accuracy, which is not very impressive. We improve the model by adding a cross feature column, which ensures we capture every combination of the crossed columns. We improve the model slightly because we are expanding the models ability to see relationships between features. Howeveer, Our model is still pretty poor. In the predicted probability histogram, we see that although there is are positive prediction and negative prediction poles, as we would expect for a binary classification, the poles are relatively spread out. We are not seeing the model being strongly confident in its predictions. The ROC Curve also shows that the model is not strongly predictive, as the curve does not bow away from the diagonal (equally likely for a positive to be true or false) that strongly.
