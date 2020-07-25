# July 20th, 2020 Lecture Response
Cats and Dogs

1. We are using RMSprop for the optimizer on the cats and dogs data. It works by looking at the past two gradient signs and multiplicatively accelerating/decelerating based on the change of signs. RMSprop deviates from its predessor (rprop) by dividing by the gradient by the square root of the mean square to produce similar results across mini-batches. On saddle points, RMSprop seems to converge to a minima quicker than stocastic gradient descent and through a more direct path than a momentum optimizer.

2. We used binary cross entropy for the loss function on the cats and dogs data, as we have two label options. The function works by training a logistic regression sigmoid curve denoting the probability of something being one of the two labels. We then take the negative log of the probabilities and compute the mean of all the losses. Using the negative log provides a strong penality for probabilities close to zero. Binary cross-entropy is often the default loss function for binary problems, proving its worth as a general loss function.

3. The metric argument provides a judgement of our model's performance that does not affect the training of the model. It's an indepenent judgement of the model from the loss function which defines how the model evolves.

![16](/DATA310_Images/20_1.png)
![16](/DATA310_Images/20_2.png)

4. The model's validation accuracy and loss diverge from the accuracy and loss of the training data by the fourth epoch. The accuracy of the validation data stagnates at around 80% while the training accuracy reaches 95%, meaning our model is significantly overfit.

![16](/DATA310_Images/zoo0.png)
![16](/DATA310_Images/zoo1.png)
![16](/DATA310_Images/zoo2.png)
![16](/DATA310_Images/zoo3.png)
![16](/DATA310_Images/zoo4.png)
![16](/DATA310_Images/zoo5.png)

5. The model performed relatively poorly on the above testing images. It is not readily discernable that the answers it gets right are not pure luck. Perhaps a larger amount of more diverse data would improve the model's accuracy, but augmenting the available images (i.e.: flipping, shearing, and rotating them) would likely provide a quicker and cheaper improvement.
