# July 28th, 2020 Lecture Response
---
## Word Embeddings
![TensorImg1](https://raw.githubusercontent.com/tensorflow/docs/master/site/en/tutorials/text/images/one-hot.png)
![TensorImg2](https://raw.githubusercontent.com/tensorflow/docs/master/site/en/tutorials/text/images/embedding2.png)
 1. One-Hot encoding uses space wastefully. As seen above, most elements of the encoding will inevitably be zero. For word embeddings, all space in the encoding array is used, and the relative direction of each vector tells us about its relationship to other words. For instance, words associated with positive movie reviews will be predicted to all generally point in the same direction in n dimensional space. The differences between two terms will also be similar to the difference between two related terms (i.e.: Man minus Woman = King minus Queen).
--- 
 ![Graph](/DATA310_Images/28_0.png)
 ![Graph](/DATA310_Images/28_1.png)
 
 2. The validation accuracy and loss appear to diverge from the training accuracy and loss significantly at around the 3rd epoch. Although the final accuracy on the validation data is still good (around 0.83), the model is certainly overfit.
---
 ![Graph](/DATA310_Images/28_2.png)
 
 3. The locations of the embedding vector tips appears to correlate with the positivity or negativity of the word. More specifically, it correlates with whether a certain word is strongly predictive either way for review score.
---
## RNN Text Classification
**Base Model**

 ![Graph](/DATA310_Images/28_3.png)
 ![Graph](/DATA310_Images/28_4.png)
 
**Adding two LSTM Layers**

 ![Graph](/DATA310_Images/28_5.png)
 ![Graph](/DATA310_Images/28_6.png)
 
 1. The model did not seem to significantly improve with two Long Short-Term Memory Layers. For the validation loss, we see a near consistent and quicker increase with the LSTM layers than we do without them, where the loss appears to begin decreasing at the end. The validation accuracy stagnants around 0.83 both with and without the LSTM layers; however, the accuracy is more sharply decreasing without the LSTM layers, so it is possible the LSTM model would fare better than the LSTM-less model over more epochs.
