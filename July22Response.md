# July 22nd, 2020 Lecture Response
## Boosted Trees

1. A one hot encoded column codes a feature as a list of binary labels ordered according to the encoder and denoting if an observation belongs a category. It is used to incorporate categorical (discrete) data into our models without the model falsely attributing meaning to the order of the numerical labels for the categories.

2. A dense feature is a combination of all of the featue columns into one array. Having all features be considered equally could make learning more efficient and allow our model to learn patterns unseen if all the columns were separated.

 ![Hist](/DATA310_Images/22_0.png)
 ![Hist](/DATA310_Images/22_1.png)
 ![Hist](/DATA310_Images/22_2.png)
 ![Hist](/DATA310_Images/22_4.png)
 ![Hist](/DATA310_Images/22_3.png)
 
3. Our boosted trees model appears more confident in its predictions than the linear model, as the probability density diagram and histogram show the positive prediction peak being shifted towards the middle. The ROC curve for the boosted trees model adheres much closer to the left edge and ceiling of the graph than the linear model's, indicating that there is more certainity that a given positive is a true positive than there is in the linear model.

---
## Boosted Trees with Model Understanding
![Hist](/DATA310_Images/22_5.png)
![Hist](/DATA310_Images/22_6.png)

1. The feature most strongly contributing to the prediction is "sex." If a given passenger is male, that is a strong indication that they did not survive. Being 31 carries a similar negative predictive contribution, and being second class or on an unknown deck cary slightly smaller (but still large) negative predictive contributions. A fare of 26.25 held the strongest positive predictive contribution (though a much smaller magnitude than the above listed negative predictors).

 ![Hist](/DATA310_Images/22_7.png)
 ![Hist](/DATA310_Images/22_8.png)
 ![Hist](/DATA310_Images/22_9.png)
  
2. Across all three feature importance graphs, sex is by far the most predictive feature. Class and age also has significant predictive power across the three graphs. 

 ![Hist](/DATA310_Images/22_11.png)
 ![Hist](/DATA310_Images/22_10.png)
 ![Hist](/DATA310_Images/trees.gif)

3. By far, the Boosted Trees model was more effective in reproducing a synthetic function. The linear model appears to have produced a relatively flate plane, while the boosted trees allows us to see the strucutre of the synthetic function even with a small number of trees.
