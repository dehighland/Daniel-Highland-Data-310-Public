# Final Project Writeup
---
+ [Poster](https://github.com/dehighland/Daniel-Highland-Data-310-Public/blob/master/DATA310_Images/PoePoster.pdf)
+ [Presentation](https://docs.google.com/presentation/d/11O8A85CxwdFev25K6BQpjWPnU_1C19AhFvJHG73Fcy4/edit?usp=sharing)
+ [Presentation Script](https://docs.google.com/presentation/d/144kQP9BXnLJUHssBJZw1q9iHKQuUzfewuI-Wp_kxYjs/edit?usp=sharing)

## Problem Statement: 
 - With the massive growth of social media, efforts to programatically determine sentiments in written text have become an increasingly prevalent fixture of machine learning study. While this technology has wide ranging applications, the insights into public health and psychology are perhaps its most beneficial use. Recent reserach has found that depression is tied to increased self focus and increased use of words with negative affects (Bernard et al). Using the works of Edgar Allan Poe as a test case, I hope to demonstrate the viability of natural language processing and sentiment analysis in tracking his mental decline through these sublte changes in his vocabulary over time. By studying an intensively biographed indivual, we can measure the accuracy of our sentiment analysis against known events in Poe's life. In addition, by studying his fiction, we can see if these changes in speech carry over into his fiction.

#### Citation:
+ Bernard, Jared D, Jenna L Baddeley, Benjamin F Rodriguez, and Philip A Burke. "Depression, Language, and Affect: An Examination of the Influence of Baseline Depression and Affect Induction on Language." Journal of Language and Social Psychology 35.3 (2016): 317-26. Web.

## Sources of Data:
 + https://www.eapoe.org/works/poems/index.htm#collections
 + I used eapoe.org as my source for Poe's stories. 
    + This website contains detailed accounts of the publication history of each of Poe's stories and poems. 
    + I focused on Poe's stories because I was concerned that the stylization of Poe's Poems might throw off the sentiment analysis. 
    + I manually copied all of his stories into individual text documents and minorly edited the documents to fix any minor formatting issues. 
    + The text files were named with an abbreviated title and the three letter month and year.
    + ![DataImage](/DATA310_Images/dataimage.JPG)

## Methodology
+ I zeroed in on Poe's wife Virginia first showing symptoms of tuberculosis as a likely inflection point in Poe's life.
     + [Link to chapter of biography by Arthur Hobson Quinn that describes the event](https://www.eapoe.org/papers/misc1921/quinnc13.htm)
+ As a proof of concept, I first used a four layer RNN model from the Google Tensorflow website. 
     + ![TensorModel](/DATA310_Images/model.JPG)
     + This model was fairly overfit and produced wildly inconsistent results with the Poe stories between runs
     + Google's model only provided sentiment polarity, so I had to expand my horizons to pick up on other attributes of the text
     + This model was trained on movie reviews, which I felt was a poor fit for mental health research
+ I moved to using TextBlob     
     + TextBlob is a simplified subset of the larger and more indepth Natural Language Toolkit library. 
     + TextBlob greatly reduces the complexity of setting up a model and training embeddings at the cost of low visibility on how it does so. 
     + To process the data, I went through each text file of Poe's stories and split the name along the dash to keep the title in dataset while converting the month and year into a datetime object. 
     + The contents of each story then had both their sentiment polarity and sentiment subjectivity recorded. In each of these graphs I plotted the raw data in blue and the average per year in orange. 
     + I also plotted sentiment polarity against sentiment subjectivity and used a color spectrum starting at blue and ending at red to see if there was any combined relationship between the two variables.
+ After this point, I lost my power for a day and then suddenly had a roommate who I needed to drive places, so I moved towards finishing the project presentation instead of improving the project proper

## Results
### Early tensorflow results
#### Model metrics:
![acc](/DATA310_Images/acc.png)
![loss](/DATA310_Images/loss.png)
#### Output
![tensor](/DATA310_Images/PoeTest.png)

 + My first results using the tensorflow model indicated that Poe's sentiment polarity nosedived right before his death. After rerunning the model several times, there seemed to be no consistentcy between runs, so I knew this model was not my stopping point.
 
 ### TextBlob results
 ![Polarity](/DATA310_Images/PoeTBPolarityBoth.png)
 ![Subjectivity](/DATA310_Images/PoeSubjectiveBoth.png)
 
 + In both graphs, blue is all stories (each dot is a single short story) and orange is the average score of all the short stories that year
 + The TextBlob model showed no indication that there was a distinct shift in Poe's polarity across his works. 
 + My prediction that Virginia developing TB seems to be supported by the graph of the subjectivity of Poe's works, as that date seems to roughly mark a sudden shift to more objectivity. 
     + This result could mean that Poe having to face the mortality of his wife influenced him to be more grounded in his writing. 
 + I found no way to access the accuracy of TextBlob on the data
     + I looked a various passages using TextBlob and they seemed correctly described by the sentiment scores, but I could not have an overall metric of model accuracy.

## Challenges and Future
+ The key issue I need to deal with is how to calibrate polarity and subjectivity, especially towards 19th Century Dialect
    + I also need to be able to access the quality of my model in a clear way.
    + After having time to think again after finishing the showcase, I think this iteration of the project would have been better if I avoided TextBlob and instead built my own RNN.
        + I moved to TextBlob because I perceived that it was probably more accurate than basing the sentiment of Poe's stories on movie reviews
        + Though I am probably right in that assessment, I should I turned instead towards training an RNN on [other data](https://www.kaggle.com/kazanova/sentiment140)
        + The process of tweaking the RNN would have been more educational for me and more entertaining as a presentation
+ In future presentations, I should emphasize the process that I took to get to my result more
        + I avoided showing the tensorflow model in my showcase presentation because I wanted to make sure my presentation was clear and didn't devolve into my listing off what I did in a rambley fashion, but I overcorrected.
+ I hope to work on this project some more once I have some freetime and look into developing it in a more professional way

-Daniel Highland
