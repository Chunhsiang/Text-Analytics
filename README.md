### The Voice YouTube Comment Analysis

## Introduction
Is there anything more frustrating than watching your favotrite singer got eliminated in TV shows like The Voice? Looking at our super star leaving the stage, we can help but feel he or she doesn't deserve this and wonder whether the judges or the mentors are making the right decisions? Are the judges choosing the less popular singers instead of the great singers that are more popular? If so, how do we identify those who are more popular online and have a greater potential to sucess in their career?

In order to answer these questions, we scrapped the youtube comments for Round2 singing videos in The Voice season 14 as our reseach data. In this round of the competition, each mentor can choosed to save one among four singers who are about to be eliminated from the game. We started with topic modeling to understand what people talk about when commenting on The Voice singing competitions, then applied sentiment analysis to extract popularity in YouTube comments, and used cosine similarity to find season 14 singers that got similar comments with successful singers who got eliminated in previous seasons in The Voice.

Sine most of my works are on sentiment analysis, I will share more detail on how we applied and improved sentiment analyis by VADER in this README.

## Sentiment Analysis

# Data Processing
To start with, we changed the emojies people left in their comments into English words. For example: 😀 was changed into "smile face". Which makes processing data easier and allowes VADER to capture the sentiments in these emojies.
![emojies](https://user-images.githubusercontent.com/31845611/47969746-e9836a80-e041-11e8-90ba-af9c51c48380.png)

# Sentiment Computation: Team Level
Next, we worked on extracting the sentiment of each comment using VADER in Python's nltk module. We aggregated sentiment of each mentor's team and visualized the sentiment distribution of each team by boxplot. 
![boxplot](https://user-images.githubusercontent.com/31845611/47969891-ab874600-e043-11e8-913c-d009e34fb148.png)
We found that, sentiment distribution in Alicia's team is different from other teams. To understand what happened we looked into the YouTube comments of singers in her team. And discovered the key to polish the performance of sentiment analysis specified for The Voice singing contest.


