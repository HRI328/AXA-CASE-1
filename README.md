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

(need follow up action, issue sorted, and not sure), which are identified after clustering through read some customer message. Off 200 message, 100 are identified as sorted, 80 are follow up, and 20 not sure. 
In order to check the accuracy for this clusterring algorithm, the PCA analysis is done using the embedding data from the text message, which shows first two components include over 90% information. These two components are used to generate the scatter plot coloured by the label identified by k-mean, which shows that three groups are clearly separated as shown in the following. This means this sentiment analysis result is reliable. 
![image](https://github.com/user-attachments/assets/62733966-87da-49dc-a06f-947fbdcdfe56)


Application
The code is saved in Github. If you are interested in the sentiment analysis, you could download the code using the link https://github.com/HRI328/AXA-CASE-1/blob/main/sentiment_analysis.ipynb.
This code is written in Google Colab. If you use Google Colab, you could manually upload your data to Google Colab, then play this code directly. If you use orther IDE, you need to make a little code modification accordingly to input data.

Accoracy Check
The data used here has total 200 text message. They are clustered into three groups (need follow up action, issue sorted, and not sure), which are identified after clustering through read some customer message. Off 200 message, 100 are identified as sorted, 80 are follow up, and 20 not sure. 
In order to check the accuracy for this clusterring algorithm, the PCA analysis is done using the embedding data from the text message, which shows first two components include over 90% information. These two components are used to generate the scatter plot coloured by the label identified by k-mean, which shows that three groups are clearly separated as shown in the following. This means this sentiment analysis result is reliable. 
![image](https://github.com/user-attachments/assets/62733966-87da-49dc-a06f-947fbdcdfe56)




