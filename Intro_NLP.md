### Why is NLP hard?

1. Language ambibiguity : Structural
2. Language imprecision and vagueness
3. News headlines

Ambiguity is the primary difference between natural and computer languages.


### NLP Model Pipeline

__Input Text -- > Preprocessing -- > Feature Extraction -- > Text mining using ML algorithms -- > Model Evaluation__

## Popular Python packages for NLP

* __NLTK (Natural Language Toolkit):__ It provides tools for tasks such as tokenization, stemming, lemmatization, part-of-speech tagging, parsing, and more.
* __spaCy:__ spaCy is a modern NLP library which offers features like tokenization, POS tagging, named entity recognition (NER), dependency parsing, and sentence segmentation.
* __TextBlob:__ TextBlob is built on top of NLTK and provides a simpler interface for common NLP tasks such as tokenization, POS tagging, noun phrase extraction, sentiment analysis, and more.
* __Gensim:__ Gensim is primarily focused on modeling and document similarity analysis.
* __scikit-learn:__   It  includes utilities for text preprocessing, such as CountVectorizer and TfidfVectorizer for converting text data into numerical feature vectors
  
---

## Three forms of Normalization


1. __Case Folding__ - Reduce all letters to lower case . It is applied in sentiment analysis, information extraction etc.
2. __Stemming__ - Reducing terms to their stems by cutting off prefix or suffix and this need not be a dictionary word. Eg: example → exampl; compressed → compress; are → ar
3. __Lemmatization__ - Reducing words to their base form i.e their dictionary words. Eg: am, are, is → be; eat, ate, eaten → eat; Write, wrote, written → write


![alt text](image-4.png)

---

## Word Representation Algorithms

1) __One-hot encoding__

*  Each word is represented as a m x 1 dimentional matrix
*  All the entries in the vector are zero except one position which is associated with the index of that word.
  
2) __BoW - Bag of Words__

* Tokenize the sentences and create the vocabulary.
* Count the no. of occurences of tokens in each sentence.
  
3) __Term Frequency - Inverse Document Frequency (TF-IDF)__

* Importance of words in document
![alt text](image.png)
 dt - no. of times term t appears in D - document, T -  total no. of terms

* Inverse Document Frequency of a term
![alt text](image-1.png)
 𝑑𝑓 (𝐷, 𝑡) is the number of documents with term t in it, N is the number of documents 
  ![alt text](image-2.png)

--- 

## Linguistic Analysis

Language is ambiguous, structured and context dependent

__Morphology__ - Structure of words - Tokenization, Stemming, Lemmatization
__Syntax__ - Structure of sentence - POS Tagging, Parsing, Dependency Trees
__Semantics__ - Meaning of sentence - Sentiment Analysis, Question Answering
__Traditional NLP__ - Explicit rules for morphology, syntax, semantics
__Modern NLP (BERT, GPT)__ -  Learn these patterns automatically from data


## Morphological Analysis

Identifying root + affixes and grammatical features.

1. __Bound Morphemes:__ Cannot appear as a word by itself. Eg: -s(dog-s), -ly (quick-ly)

2. __Free Morphemes:__ Can appear as a word by itself and can often combine with other morphemes too. Eg: house (house-s), walk (walk-ed)
3. __Content morphemes:__ Carry some semantic content. Eg: car, book, house 
4. __Functional morphemes:__ Provide grammatical information. Eg: A, the, he
5. __Inflectional morphology:__ Creates new forms of the same word :  bring, brought, brings. It changes function within a sentence
6. __Derivational morphology:__ Creates new words by changing part-of-speech: logic, logical, illogical. It changes the word itself

* __Stems:__ The core meaning bearing units. Stems are free morphemes 
* __Affixes:__ Bits and pieces adhering to stems to change their meanings and grammatical functions. 

---

## Semantics

### Distributional Semantics

A word's contexual representation with the help of contexual cues. 

---

## Word Embedding


Neural Networks:

1.  Continuous bag of words (CBOW)  : Predict focus word from context word
2.  Skip Gram Model: Predict context from focus word
  
![alt text](image-6.png)

## Limitation of Word2vec

1. __Out of Vocabulary (OOV) Words:__
Embedding is created for each word. It can't handle any words that is not in the training embedding

2. __Morphology__
For word with same radicals like "eat" and eaten", it doesn't do any parameter sharing

---

## CBOW

It is a 3 layer neural network. The context words from the input layer. Each word is encoded in one hot form. A single hidden and output layer. If the probablity of the output layer is not between 0 and 1, softmax layer is applied.

![alt text](image-5.png)

---

## N- Gram Model Probablity

![alt text](image-3.png)
