# The Voice YouTube Comment Analysis

## Introduction
Is there anything more frustrating than watching your favotrite singer got eliminated in TV shows like The Voice? Looking at our super star leaving the stage, we can help but feel he or she doesn't deserve this and wonder whether the judges or the mentors are making the right decisions? Are the judges choosing the less popular singers instead of the great singers that are more popular? If so, how do we identify those who are more popular online and have a greater potential to sucess in their career?

In order to answer these questions, we scrapped the youtube comments for Round2 singing videos in The Voice season 14 as our reseach data. In this round of the competition, each mentor can choosed to save one among four singers who are about to be eliminated from the game. We started with topic modeling to understand what people talk about when commenting on The Voice singing competitions, then applied sentiment analysis to extract popularity in YouTube comments, and used cosine similarity to find season 14 singers that got similar comments with successful singers who got eliminated in previous seasons in The Voice.

Sine most of my works are on sentiment analysis, I will share more detail on how we applied and improved sentiment analyis by VADER in this README.



## Sentiment Analysis

### Data Processing
To start with, we changed the emojies people left in their comments into English words. For example: 😀 was changed into "smile face". Which makes processing data easier and allowes VADER to capture the sentiments in these emojies.

![emojies](https://user-images.githubusercontent.com/31845611/47970012-66fcaa00-e045-11e8-9728-bcb241c3b8aa.png)


### Sentiment Computation: Team Level
Next, we worked on extracting the sentiment of each comment using VADER in Python's nltk module. We aggregated sentiment of each mentor's team and visualized the sentiment distribution of each team by boxplot. 

![boxplot](https://user-images.githubusercontent.com/31845611/47969989-14bb8900-e045-11e8-907e-ca6e42a13561.png)

We found that, sentiment distribution in Alicia's team is different from other teams. To understand what happened we looked into the YouTube comments of singers in her team. And discovered the key to polish the performance of sentiment analysis specified for The Voice singing contest.


### Understanding context and improved sentiment dictionary

![screen shot 2018-11-05 at 10 56 47 am 2](https://user-images.githubusercontent.com/31845611/48013720-8bf72880-e0ea-11e8-898d-2bf4c174a9d1.png)

Among the four competitors in this round of Alicia's team, Christiana was chosen by Alicia to proceed to the next round. However, Kelsea has also put up a great performace and have more strong supporters on YouTube. When Kelsea's supporters comment on YouTube, many of them say things like: feeling bad for Kelsea, angry at the mentor's choice, upset about the results, etc. In other words, these negative words in the comment are pointing at the competition instead of of Kelsea and her singing performance. If we look at the sentiment at a team level, people are feeling bad to what has happened in Alicia's team. Nevertheless, when looking at an individual's singing contest vedio, these negative comment words left under the vedio actualy conveys a positive sentiment to the individual singer.

![sentiment_dict](https://user-images.githubusercontent.com/31845611/48015352-94516280-e0ee-11e8-9804-e000a8bba74f.png)

To improve our sentiment analysis, we adjust the sentiment dictionary based on our finding. Which gave us surprising results that we consider closer to the reality. In the plots below, the orange bars are the average sentiment scores of the singers chose by mentors, and the blue bars show those who are eliminated. We can see that in three out of four teams, there are discrepencies between the mentor's choice and the singer's popularity on YouTube. Such result correspond to the like - dislike ratio on each singer's competition YouTube vedio, and our understanding of how people feels after looking at the comments manually.

![sentiment_after](https://user-images.githubusercontent.com/31845611/48015965-f6f72e00-e0ef-11e8-887b-3ec10544bca6.png)




