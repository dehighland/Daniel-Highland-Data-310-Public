# July 15th, 2020 Lecture Response
---
## Convolutional Horses and Humans
 1. ImageDataGenerator generates tensor image data with real time data augmentation (per documentation). One argument it has is 'rescale,' which changes the scale of the pixel values of an image. We do this to get the values on the scale of [0,1]. To flow it from a directory, we need to define the string name of the source directory, the target size for the images, the batch size, and the class mode. The target size defines the scale all images that enter our model should be, changing images of any other scale to the desired scale. The class mode defines how we want our images classified. Because we only intend it to make a choice between two categories, we used binary for the class mode. For the validation dataset, you use the same settings for ImageDataGenerator and a smaller batch size for the flow_from_directory compared to the training dataset.
2. Our CNN has three 2D convolution and max pooling pairs followed by a flattening layer and two dense layers. The images sizes decrease by 2 with each 2D convolution and halved by each max pooling layer before being flattened into one a large one dimensioned ouput that connects to a 512 sized output and finally a single output (binary) dense layer. Each 2D Convolution layer has an increasing number of filters, which start at 16 and end at 64. The final output layer has a sigmoid activation, which essentially choses 1 or 0. In the compiler, which specify binary_crossentropy as out loss function, because we have two output options, and RMSprop with a learning rate of 0.001 as our optimizer. Our metric is 'accuracy.'
---
## Regression
  1. 
  ![Seaborn Pair Plot](/DATA310_Images/Lecture7152000.png)
  - We can see rough shapes in the co-relationship graphs, such as linear or exponsential growths and decays. We can use this to pick out relationships that have strong correspondence and focus on them for our model. For instance, weight and displacement have a pretty tight linear shape, so we could train our dataset soley on them (or with other highly correlated variables). The diagonal graphs show probability densities for the variable which defines both axises (the y axis is mislabeled). This function shows if the values for a given variable are skewed towards any direction or if there is any separation/poles.
  2.
### Loss on Training Data
  ![Train Loss](/DATA310_Images/Lecture7152001.png)
### Loss on Validation Data
  ![Val Loss](/DATA310_Images/Lecture7152002.png)
  - The model appears to move slightly up and down on the loss, mae, and mse for both the training and validation data. With smoothing, we can see that the stats for the validation data are generally increasing after epoch 920, while the training data's stats are generally decreasing until the final 10 epochs. We can deduce from these graphs that we should include less epochs (perhaps 920, but we should explore the data more first).
---
## Overfitting and Underfitting
### Loss on Models of Various Sizes
 ![Various Models](/DATA310_Images/Lecture7152003.png)
 - The different models demonstrate the effect of the number of parameters on the fitting of the model. We can see the number of parameters directly relates to how fast the training data decreases. As the number of layers increases in our models, there is a quicker and quicker drop off in the loss. For the validation data, we see that the medium model reaches its lowest loss somewhere before 100 epochs, which is much less epochs than either the tiny or small models take to get to a similar level of loss. The large model, however, fails to reach this level of loss, instead diverging from the model's performance much quicker and more immeadiately steeper than the medium model.
