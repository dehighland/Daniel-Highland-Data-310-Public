# Project 3: Accra Population Estimator
---

  This project is an attempt to approximate human population within 10,000 birds eye photos (orthophotos) of Accra, Ghana. These images were compiled together into a single folder for ease of importing, and then randomly split into groups of 9000 and 1000 to delineate training and testing images, respectively. For every picture in these groups the filename was used to load the image with a target size of 150x150 for memory space and divide it by 255 to normalize its values. This same filename is then converted to its integer name and used to append the image's population score from a dataframe of a labels csv file. Because the same file name is used for fetching both the images and the labels, the labels match the images' array positions. I first used a 3 layer deep neural network to make sure the data was formatted correctly. This deep neural net had a flatten, a dense 128, abd dense 10 layer with softmax as the final activation, and it was compiled with sgd as an optimizer and mean average error as the loss function. The validation data had a mean average error of 53.4, so it definitely needed improvement. I then moved on to the following convolutional network:

 + ![MAE](/DATA310_Images/25_00.JPG)

  A convolutional network should improve our model, because population in our images is correlated with the number of houses visible and, therefore, convolutional filters should be able to pick out edges in the images. RMSprop was used as the optimizer to speed up the optimization, and Huber loss was picked because it and seemed to work well.

![Huber](/DATA310_Images/25_7.png)
![MAE](/DATA310_Images/25_9.png)

After using 7000 of 9000 to train the model over 50 epochs, the model appeared to stop improving its validation loss after about the 10th epoch. The final loss of the training data was around 9 and the 16.62 for the validation data. The mean average error improved from 53.4 to 17.08. 

![Accuracy](/DATA310_Images/25_8.png)

  This graph of the accuracy shows that it only started improving for the training and testing data at the end, and it was consistently tiny. One possible interpretation of this result compared to the decent Huber and MAE losses is that exact accuracy is a poor metric for this dataset. The population scores on each picture are themselves estimates with several decimal places, so it is hard to exactly land on them. Also, because the labels themselves are estimations with noise, lowering the average error is probably more predictive than fitting to the accuracy of each image. 
  
  While the model is certainly not perfect, It performed quite well on the validation images given the relatively short amount of work optimizing the convolutional model.

![PopImage](/DATA310_Images/25_0.png)
![PopImage](/DATA310_Images/25_1.png)
![PopImage](/DATA310_Images/25_2.png)
![PopImage](/DATA310_Images/25_3.png)
![PopImage](/DATA310_Images/25_4.png)
![PopImage](/DATA310_Images/25_6.png)
![PopImage](/DATA310_Images/25_10.png)
![PopImage](/DATA310_Images/25_11.png)

  While it was extremely close on multiple randomly picked photos, it was siginifacntly far from a lot of the high population images.  Also, the model seemed to consistently lowball its answers, likely because the image labels themselves skewed downward. The noisiness of the original population estimations presumably affected our predictions. Several of the low population images have no apparent population in the image, but are listed as having 7 people living in them (for instance). The fact that there is no apparent indicator that people are living in the image perhaps causes our model to find innaccurate predictors and throw off the overall predictions. However, the model nonetheless got the ballpark right (large population area or sparsely populated area).
  
  The next step in developing the model would be to implement image aumentation into our model. Because population is correlated with roads and houses, the ability to zoom and rotate our images could dramatically raise the model's predictive power. The convolutional model architecture itself also needs to be tweaked. For instance, there is no activation function on the final layer. The model's predictive power did improve over using both softmax and sigmoid for the final layer; however, I recently found a linear activation for Conv2D which could improve the model. We could also somehow add residential/commerce/etc zone labels to get more descriptive predictions and be able to change our population prediction based off of whether people actually dwell in that area.
  
  
