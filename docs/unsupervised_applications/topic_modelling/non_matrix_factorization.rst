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

.. image:: files/pics/NMF_Intro_Overview.png

As shown above, we have the document-term matrix A (Individual documents along the rows of the matrix and each unique term along the columns) which we decompose it into two the following two matrices:

	* First matrix: It has every topic and what terms in it. Each column of this matrix W represents the weightage each word gets in a sentence with respect to a particular topic.
	* Second matrix: It has every document and what topics in it.

NMF will modify the initial values of W and H so that the product approaches A until either the approximation error converges or the max iterations are reached. Therefore, by using NMF we are able to obtain factorized matrices having significantly lower dimensions than those of the product matrix. Intuitively, NMF assumes that the original input is made of a set of hidden features.

**Assumption**: All the elements of the matrices W and H are positive given that all the entries of A are positive.

