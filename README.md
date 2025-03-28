# Customer-Reviews-Model
This project ivolved the development of 3 AI models with the end goal of being able to generate blog type posts talking about the best producs based on a data set of amazon products reviews.
For that was necesary to run Sentiment analysis, clustering and sumarization. In this particual project implemented with different degrees of succes.

## Methods
The first course of action was to do some preprocessing on the data set:
- Drop duplicates: Search for reviews that where exactly the same and made sure to get rid of those and fill any empty values

## Sentiment Analisis
This was based mainly on the rating of the producs (1-5 stars):
- review <= 2 -> negative
- review = 3 -> neutral
- review >= 4 -> positive

By trial an error it became clear that the ammount of entries for each sentiment was hugely unbalanced. To prevent this some undersampling of the biggest class was performed at the same time as some oversampling to add sythetic values to the smallest class witch helped greatly improve the precision specially for the negative reviews part.

Tthe model used for this task was a Random Forest Classifier

## Clustering
To decide the different groups for this step the dataset was inspected manualy and a guess of 6 clusters seemed the most accurate for the situation.
- Ebook
- Batteries
- Accesories
- Non electronics
- Cables and Adapters
- Smart home devices

The model used was KMeans using the name of the produc and the review as input to try and give it the most context possible. The results were of mixed quality probably due to the big ammount of ebook entries and all the variation that confused the model. 
Could probably be improved with some more cleaning of the strings that were fed to the model.

## Sumarized reviews
Runned out of time to fully implement this part of the model to a useful state. Tried several models like Flan-t5-base, T5-B7 or mistral-7B-v0.3 to no degree of succes
The models kept giving incomplete sentences or only repeating reviews of the dataset without any creative writing to imitate the style of a tech blog post.
in the end one of the only "acceptable" articles was as follows:

Article • The Amazon Echo Show and Amazon Tap
are two of the best Bluetooth speakers on
the market. The Echo Show is a version of
Alexa with ability to visualize things. The
Amazon Tap is the only Bluetooth speaker
that has a 7" screen and a built-in speaker.
The Tap is also a great speaker and Echo
substitute. If you're looking for a speaker
that's a little less expensive than the Echo
Show, this is the speaker for you. 'Amazon
Tap - Alexa-Enabled Portable Bluetooth
Speaker with 7" Screen'

## Take aways
- Being the first solo project of the bootcamp proved more challenging that expected.
- spent too much time trying to perfect the sentiment analisis witch caused to not have much time left to deal with the other models
