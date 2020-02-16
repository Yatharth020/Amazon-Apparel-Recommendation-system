# Amazon-Apparel-Recommendation-system

In this project our objective is to recommend similar products/items in e-commerce website
Amazon.So basically what we are doing here is __contect based recommendation__.Around 35% of the total revenue at Amazon.com is generated using product recommendation which is close to 40 billion dollars.That's why it becomes important to understand how will we use previous and existing data for recommneding the similar products.

## Data acquisition:
<br> Using Rest protocol we got the data using API from amazon in json form</br>

## Data Cleaning:

  -  __Missing and duplicate values imputation__
  - __Text Preprocessing___:
        <br> removing stopwords,text in lower string and using Porter Stemming 

## Modelling strategy:
 __Text based product similarity__:
  <br>First modelling strategy would be using text based features and then using cosine or euclidean similarity to find the similar products</br>
    <b>- Using Bag of words<br>
    -  Usinf TFIDF vectorization<br>
    -  Using IDF based (Weighted W2V)<br>
  
 __DL base product similarity__:
 <br>We will use VGC16 architecture for our CNN model to extract features from an image and then find similarity between the products to recommend them.</br>
 
 __Final Strategy__:
 <br>Combining all the text based features and CNN extracted features,concatenating and then finding similarity using the final dense vector.So we used Text,brand,color and CNN feature vectors.Another small hack we do is giving more weightage to each of the vectors and then finding similarity for different cases.
 
 ## Observation and Results:
 <br>
 There is a wide range of suggestions that pop up when we use equal weights for each of our four features. There is a healthy combination of Brand names, Colors and Textual similarity with the title. In general, what we observe mostly is that the suggestions are mostly related to animal names like zebra, tiger and a few other animals.

Giving more weight to IDF vectors has resulted in most of the recommendations belonging to the same brand and almost 90% of the top 20 recommendations had tiger and zebra prints specifically!

Giving more weights to brand names has resulted in suggestions which belong to the input brand, in our case we have Si Row. Almost 90% of the recommendations have the same brand name.

Here we have given more weights to colors and not to our surprise we see that most of the recommendations belonged to the same color, in our case the input color is Brown. Here again, 90% of the recommendations belonged to apparels having the same color as the query data point, i.e. Brown color.

Lastly, we have tried giving more weights to the CNN features and see how the system behaves! As we can see based solely on the CNN features, the model has picked up some really nice and diverse collections for recommendation purpose. Out query data point had a tiger image, it was white in color. The recommendations that were shown also had more or less the same features. We can see lots of diversity here including zebra stripes, tiger images, white images etc!</br>
