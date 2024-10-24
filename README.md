# AXA-CASE-1
Text message sentiment analysis for AXA

Introduction

Sentiment analysis is used to extract subjective information from text, such as a reviewer's feelings, thoughts, or judgments about a topic. It can be applied to a variety of sources, including emails, social media comments, customer support chat transcripts, and reviews. 
Here sentiment analysis is used to analysis customer's reponse in the customer phone call to identify if the issue is sorted or need following up.


Method

Data is from 200 customer call, which includes the dialoge between medical insurance member and PA agent. Here we focus on the customer's point. So only customer's speech is used. 

Because this data has not been labelled, the unsupervised machine learning algorithm, k-mean clusterring is used here. Compared with other clusterring algorithm, it is simple: easy to understand and implement, efficient: fast compared to other clustering algorithms, interpretable: easy to understand and can help derive insights.

Disadvantage of k-mean is that it couldn't determinate the number of clusters. In order to find the suitable number of clusters, the elbow method is used, which shows that the data should be classified into 4 classes as shown in the following graph.
![image](https://github.com/user-attachments/assets/dcdb2d7c-0339-4cf3-a5ac-0978537649b9)


Accoracy Check

silhouette_score is a metric to calculate the goodness_of_fitness of a clustering algorithm, which ranges from -1 to 1. 0 means clusters are overlapping and either data or the number of cluster are incorrect. 1 means cluster is ver dense and nicely separated. Negative value means element is possibly assigned to the wrong class.
Here the silhouette_score is 0.327. It is acceptable.


Decision of Physical Meaning of Cluster Label

The data used here has total 200 text message. They are clustered into four groups by k-mean model. K-mean model provides the label for each group data. We need to define the label. The method used is randomly to select some text message with the different label. After reading the label is defined as:

Label 0 and 2 : need investigation for the next step, i.e., follow up action

label 1 : sorted after investigation in the phone

label 3 : sorted


Data Insight

The following bar chart shows how many customer call in sorted and follow up action.
![image](https://github.com/user-attachments/assets/96aed703-155d-46fa-9a7d-28b928c454b9)

In order to understand more about each cluster, the text message is found using the shortest distance between the average embedding and centroid from k-mean model and the top 10 key words are extracted as the following.

From the key words in each cluster label, we could see the label 1 and 3 are mainly related to the authorization, label 0 is related to copay and refund, label 2 is related to online member account.

Key Words in Cluster Label 0
[('refund', 0.4739),
 ('copay', 0.4406),
 ('appointment', 0.3208),
 ('physician', 0.2679),
 ('customer', 0.2666),
 ('service', 0.258),
 ('doctor', 0.2525),
 ('care', 0.2365),
 ('mem123456', 0.2331),
 ('resolving', 0.206)]

 Key Words in Cluster Label 1
[('authorization', 0.4456),
 ('knee', 0.346),
 ('procedure', 0.3061),
 ('pre', 0.2967),
 ('hospital', 0.2829),
 ('arthritis', 0.2753),
 ('surgery', 0.2608),
 ('medical', 0.2538),
 ('done', 0.2375),
 ('doctor', 0.237)]

 Key Words in Cluster Label 2
[('registering', 0.5395),
 ('register', 0.4929),
 ('mem123456', 0.4555),
 ('member', 0.3951),
 ('account', 0.3901),
 ('invalid', 0.3504),
 ('id', 0.3438),
 ('password', 0.3295),
 ('entered', 0.3029),
 ('online', 0.2865)]

 Key Words in Cluster Label 3
[('deductible', 0.3304),
 ('authorization', 0.3047),
 ('procedure', 0.3026),
 ('pre', 0.2919),
 ('mem123456', 0.2306),
 ('doctor', 0.2154),
 ('1234', 0.2093),
 ('555', 0.1955),
 ('contact', 0.193),
 ('dr', 0.1872)]


Application
The code is saved in Github. If you are interested in the sentiment analysis, you could download the code using the link https://github.com/HRI328/AXA-CASE-1/blob/main/sentiment_analysis.ipynb.
This code is written in Google Colab. If you use Google Colab, you could manually upload your data to Google Colab, then play this code directly. If you use orther IDE, you need to make a little code modification accordingly to input data.


