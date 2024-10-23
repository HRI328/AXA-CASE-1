# AXA-CASE-1
Text message sentiment analysis for AXA

Introduction
Sentiment analysis is used to extract subjective information from text, such as a reviewer's feelings, thoughts, or judgments about a topic. It can be applied to a variety of sources, including emails, social media comments, customer support chat transcripts, and reviews. 
Here sentiment analysis is used to analysis customer's reponse in the customer phone call to identify if the issue is sorted or need following up.

Method
Data is from 200 customer call, which includes the dialoge between medical insurance member and PA agent. Here we focus on the customer's point. So only customer's speech is used. 
Because this data has not been labelled, the unsupervised machine learning algorithm, k-mean clusterring is used here. Compared with other clusterring algorithm, it is simple: easy to understand and implement, efficient: fast compared to other clustering algorithms, interpretable: easy to understand and can help derive insights.

Application
The code is saved in Github. If you are interested in the sentiment analysis, you could download the code using the link https://github.com/HRI328/AXA-CASE-1/blob/main/sentiment_analysis.ipynb.
This code is written in Google Colab. If you use Google Colab, you could manually upload your data to Google Colab, then play this code directly. If you use orther IDE, you need to make a little code modification accordingly to input data.

Accoracy Check
The data used here has total 200 text message. They are clustered into three groups (need follow up action, issue sorted, and not sure), which are identified after clustering through read some customer message. Off 200 message, 100 are identified as sorted, 80 are follow up, and 20 not sure. 
In order to check the accuracy for this clusterring algorithm, the PCA analysis is done using the embedding data from the text message, which shows first two components include over 90% information. These two components are used to generate the scatter plot coloured by the label identified by k-mean, which shows that three groups are clearly separated as shown in the following. This means this sentiment analysis result is reliable. 
![image](https://github.com/user-attachments/assets/62733966-87da-49dc-a06f-947fbdcdfe56)




