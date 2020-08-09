# Final Project Writeup
---
+ Poster link:
![Poster](/DATA310_Images/PoePoster.pdf)
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
     + This model was fairly overfit and produced wildly inconsistent results with the Poe stories between runs
     + Google's model only provided sentiment polarity, so I had to expand my horizons to pick up on other attributes of the text
+ I moved to using TextBlob     
     + TextBlob is a simplified subset of the larger and more indepth Natural Language Toolkit library. 
     + TextBlob greatly reduces the complexity of setting up a model and training embeddings at the cost of low visibility on how it does so. 
     + To process the data, I went through each text file of Poe's stories and split the name along the dash to keep the title in dataset while converting the month and year into a datetime object. 
     + The contents of each story then had both their sentiment polarity and sentiment subjectivity recorded. In each of these graphs I plotted the raw data in blue and the average per year in orange. 
     + I also plotted sentiment polarity against sentiment subjectivity and used a color spectrum starting at blue and ending at red to see if there was any combined relationship between the two variables.

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
