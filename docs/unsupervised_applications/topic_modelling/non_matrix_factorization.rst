Non-Matrix Factorization
****************************

Introduction
------------------------
------------------------

#. Non-Negative Matrix Factorization (NMF) is an unsupervised topic modelling technique.
#. It belongs to the family of linear algebra algorithms that are used to identify the latent or hidden structure present in the data.
#. NMF decomposes (or factorizes) high-dimensional vectors into a lower-dimensional representation.
#. These lower-dimensional vectors are non-negative which also means their coefficients are non-negative.
#. In case of topic modelling, the input is the term-document matrix, typically TF-IDF normalized:

	* Input: Term-Document matrix, number of topics
	* Output: Gives two non-negative matrices of the original n-words by k topics and those same k topics by the m original documents

#. NMF has become so popular because of its ability to automatically extract sparse and easily interpretable factors.



