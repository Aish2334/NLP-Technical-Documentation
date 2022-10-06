****************************
Latent Dirichlet Allocation
****************************



Introduction
_____________

* **Latent**: Latent refers to anything that is 'hidden' in the data. In this technique, the topics within the document are not known, but it is assumed that they are present since the text is generated based on the topics.

* **Dirichlet**: Dirichlet is a distribution of distributions.
  
  Let's say we have a machine that produces dice and each dice will have 6 unbiased sides. Additionally, we can control whether a machine will produce a dice. 	 
  In this scenario, the machine producing dice is considered as a distribution since it can produce different types of dice. The dice itself would be a distribution as each dice has 6 possible face values. This is a case of Dirichlet distribution or a 'distribution of distributions'.

* **Allocation**: Once we have a Dirichlet distribution, we allocate topics to documents and words of the document to topics.

Assumptions
_____________

#. LDA assumes that every chunk of text/document fed into it has words associated with each other.
#. It also assumes documents are produced from a mixture of topics. These topics then generate words  
   based on their probability distribution.

.. image:: LDA_high_level_overview.png


Default Parameters
___________________

* **Document-topic density factor (‘α’)**
	The ‘α’ hyperparameter determines how many topics would exist in the document corpus. A low value of ‘α’ would mean fewer topics in the document mix and vice versa
	Also known as the concentration parameter, following are the possible types of ‘α’ distribution:
		- Uniform (α =1)
		- Concentrated (α > 1)
		- Sparse (α < 1)

* **Topic-word density factor (‘β’)**
    The ‘β’ hyperparameter determines how many words are distributed to each topic. Topics with lower value of ‘β’ will have fewer words and vice versa. Like α, β can take values between 0 and 1.

* **Number of topics to be considered (K)**
    K is usually assigned a value based on domain expertise.

Algorithm Explained
___________________

*Step-1*:
Go through each of the documents in a corpus and randomly assign each word in the document to one of K topics (K is chosen beforehand or given by the user).

*Step-2*:
With the help of random assignment, we got the topic representations for all the documents and word distributions of all the topics, but these are not very good ones.

*Step-3*:
To improve on this random assignment, for each document d, we go through each word w and compute the following:

   **P (topic t | document d)**: represents the proportion of words present in document d that are assigned to topic t of the corpus.

   **P (word w | topic t)**: represents the proportion of assignments to topic t, over all documents d, that comes from word w.

*Step-4*:
Reassign word w a new topic t’, where we choose topic t’ with probability p(topic t’ | document d)* p(word w | topic t’).
This generative model predicts the probability that topic t’ generate word w.

*Step-5*:
Repeating Step-4 a large number of times, up to we reach a steady-state and at that state the topic assignments are pretty good. And finally, we use these assignments to determine the topic mixtures of each document.

*Step-6*:
After completing a certain number of iterations, we achieved a steady state where the document topic and topic term distributions are fairly good. And this becomes the convergence point of LDA.

 
.. image:: LDA_algorithm_flowchart.png


Model Execution
___________________

Add text here

Model Evaluation Metrics
_________________________

Add text here

Disadvantages
___________________

* *LDA results may not be robust* - Documents with identical wording may be stated as having wildly different topical content. Since LDA results are probabilistic, we wouldn’t necessarily expect identically-worded documents to have the exact same topical distributions. In the event that this happens, it becomes difficult to differentiate between such documents. 

* *LDA results may not be explicable* - The results of an LDA give probability distributions for the topics over the vocabulary. In order to understand what each topic is about 'semantically', we can list the words in order of decreasing probability, and look at the top j words per topic for some j. Thus, we are looking at a list of words that is somehow representative of this topic. But these words typically don’t fit together in an easily-comprehensible way. We don’t usually get a list like:

    - Topic x: banana, orange, grapefruit, peel, vitamin, five, watermelon.
     
  Thus, we need to strongly rely on guess-work to find the best possible semantically appropriate topic for a set of its top words.

