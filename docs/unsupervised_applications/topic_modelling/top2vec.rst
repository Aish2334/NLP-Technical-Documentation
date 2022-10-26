Top2Vec
****************************

Introduction
------------------------
------------------------

Top2Vec model is an easy to implement state-of-the art model used for unsupervised machine learning that automatically detects topics present in text and generates jointly embedded topic, document and word vectors. The number of dense areas of documents found in the semantic space is assumed to be the number of prominent topics. The topic vectors are calculated as the centroids of each dense area of document vectors.

Important usage of Top2Vec is as follows:

	- Obtaining the number of detected documents 
	- Get content and size of the topics
	- Finding the hierarchy in topics
	- Using keywords to search topics
	- Using topics to search document
	- Using keywords to search documents 
	- Finding similar words
    - Finding the same documents


Algorithm Explained
------------------------
------------------------

Following are the steps in this modelling technique:
	- Word and Vector embedding
	- UMAP Dimensionality Reduction
	- HDBSCAN Clustering
	- Centroid calculation and topic assignment

Word and Vector embedding
____________________________

This step includes the generation of embedding vectors that allows us to represent the text document in the mathematical framework. This framework can be multi-dimensional where the dimension depends on the word or text document. This can be performed using `Doc2Vec`_ or `Universal Sentence Encoder`_ or `BERT Sentence Transformer`_.

.. _BERT Sentence Transformer: https://medium.com/@janhavil1202/understanding-topic-modeling-with-top2vec-cdf58bcd6c09
.. _Doc2Vec: https://medium.com/wisio/a-gentle-introduction-to-doc2vec-db3e8c0cce5e
.. _Universal Sentence Encoder: https://tfhub.dev/google/collections/universal-sentence-encoder/1

