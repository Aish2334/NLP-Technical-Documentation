BertTopic
****************************

Introduction
______________

BERTopic is a topic modeling technique that leverages BERT embeddings and a class-based TF-IDF to create dense clusters allowing for easily interpretable topics whilst keeping important words in the topic descriptions.

There are four key components used in BERTopic, those are:

	* A transformer embedding model
	* UMAP dimensionality reduction
	* HDBSCAN clustering
	* Cluster tagging using c-TF-IDF

.. image:: ../pics/BERTopic_overall_flowchart.png


Transformer Embedding
------------------------
------------------------

* The first step is to embed documents into dimensional vectors.
* BERTopic supports several libraries (Sentence Transformers, Flair, SpaCy, Gensim, USE TF Hub) for encoding our text to dense vector embeddings. Of these, :ref:Sentence Transformers `https://www.pinecone.io/learn/sentence-embeddings/` library provides the most extensive library of high-performing sentence embedding models. 
