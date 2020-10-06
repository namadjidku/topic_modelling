# Topic Modelling

Latent Dirichlet Allocation (LDA) is used to classify text in a document to a particular topic. It builds a topic per document model and words per topic model, modeled as Dirichlet distributions. 

* Each document is modeled as a multinomial distribution of topics and each topic is modeled as a multinomial distribution of words.
* LDA assumes that the every chunk of text we feed into it will contain words that are somehow related. Therefore choosing the right corpus of data is crucial. 
* It also assumes documents are produced from a mixture of topics. Those topics then generate words based on their probability distribution. 

The dataset used is a list of over one million news headlines published over a period of 15 years.
To process the dataset the following steps were performed:

* **Tokenization**: Split the text into sentences and the sentences into words. Lowercase the words and remove punctuation.
* Words that have fewer than 3 characters are removed.
* All **stopwords** are removed.
* Words are **lemmatized** - words in third person are changed to first person and verbs in past and future tenses are changed into present.
* Words are **stemmed** - words are reduced to their root form.

Convert document (a list of words) into the bag-of-words format = list of (token_id, token_count) 2-tuples. Each word is assumed to be a tokenized and normalized string (either unicode or utf8-encoded). 

Following is an overall scheme of the algorithm: 

[image1]: ./LDA.jpg
[image2]: ./training.jpg

![image1]

By comparing the generated fake documents with the real ones, we can compute the error and backpropogate it to compute the gradient and move the points to reduce the error:
![image2]

Implementation of LDA is not the part of the project, the described logic is carried out by the library gensim. 
