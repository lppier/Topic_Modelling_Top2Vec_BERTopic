# Topic_Modelling_Top2Vec_BERTopic

Blog Article Here : https://lppier.github.io/topic-modelling-alt-to-lda

## Abstract

Exploration of 2 interesting libraries designed to improve upon topic modelling. One is Top2Vec and the other is BERTopic.

Top2Vec makes use of 3 main ideas :

Jointly embedded document and word vectors
UMAP as a way of reducing the high dimensionality of the vectors in (1)
HDBSCAN as a way of clustering the document vectors
The n-closest word vectors to the resulting topic vector (which is the centroid of the dense clusters in step 3) are then the topic words describing that particular topic.

Top2Vec has the following advantages :

Automatically finds number of topics.
No stop word lists required.
No need for stemming/lemmatization.
Works on short text.
Creates jointly embedded topic, document, and word vectors.
Has search functions built-in.
Language agnostic if you use the doc2vec method
Top2Vec defaults to a doc2vec model for the embeddings, but you can also use universal sentence encoder or a sentence-transformer based model for embedding the vectors.

The author has a detailed write-up on how Top2Vec works here in his paper. https://arxiv.org/abs/2008.09470

BERTopic, on the other hand, is a topic modelling technique that leverages transformers and Cluster-based Term Frequency/Inverse Document Frequency (c-TF-IDF) to create dense clusters allowing for easily interpretable topics. It also finds the number of topics automatically and has most of the advantages that Top2Vec has. It follows similar methods of Top2Vec of doing the dimensionality reduction method of UMAP followed by HDBSCAN to do clustering. What is does differently is that it uses c-TFIDF to determine the topic words. The intuition is that instead of comparing the importance of words between documents, the author compares the importance of words between the different clusters.

The dataset used was from https://github.com/philipperemy/financial-news-dataset You may need to email and get the articles indirectly via email. I only used the articles from 2006-2010, setting out to discover the topics that occurred during this period.

