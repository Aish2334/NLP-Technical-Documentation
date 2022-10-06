BertTopic
****************************

BERTopic is a topic modeling technique that leverages BERT embeddings and a class-based TF-IDF to create dense clusters allowing for easily interpretable topics whilst keeping important words in the topic descriptions.

There are four key components used in BERTopic, those are:

	* A transformer embedding model
	* UMAP dimensionality reduction
	* HDBSCAN clustering
	* Cluster tagging using c-TF-IDF

.. image:: ../pics/BERTopic_overall_flowchart.png