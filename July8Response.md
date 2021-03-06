# July 8th, 2020 Lecture Response
 1. The dataset is split because machine learning works by decerning rules/relations from data, so we need to input data with their correct labels to teach the model. However, if we want to know how well our model actually works (it could have simply just memorized the training set), it needs to be tested on data it hasn't seen before. This exercise didn't use the testing set, but in the future it will inform us of the quality of our models.
 2. Relu sets the minimum boundary as zero (any negative values is changed to zero) in order to prevent negative results cancelling out positive outputs and thereby skewing our results. Softmax sets the neuron in the final layer with the maximum value to 1 and all other neurons in the output layer to 0, thereby making the choice of which output to classify with much easier (we have to pick the 1, not look through all the neurons to find the maximum). 
 3. The loss function is simply a calculation of how wrong the model at its current iteration is compared to the training answers. For our first example, we judged "wrongness" by the mean squared errors between the iteration's answer and the real answer, but we use sparse_cateforical-crossentropy here because it is suited to finding "wrongness" in computer vision cases. The optimizer is effectively the response to the loss function. Its goal is to lessen the loss function by shifting the parameters according to particular optimizer function used. Last time we used stocastic gradient descent, which pulled the parameters down approximately along the loss gradient (the steepest slope) to a minimum value.
 
 4. 
     - The training images set is of 60,000 28x28 pixel written numbers.
     - The training labels has length 60,000 (one label for each image).
     - The testing images set has 10,000 28x28 pixel images.
     - ![](lecture782000.png)
