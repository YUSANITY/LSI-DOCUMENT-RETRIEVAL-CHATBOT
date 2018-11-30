# LSI-DOCUMENT-RETRIEVAL-CHATBOT
### Methodology
The chatbot will be created based on a document retrieval based chatbot architecture. It will be trained on a set of questions 
and answer dataset. When a user queries a question, the chatbot will find the most relevant answers in the set of possible 
response and then outputs the answer.

### Data Requirements
The Data required to train the chatbot need to be in a question and answer format. To obtain the best possible result, 
the questions and answer should be in a more generic nature regarding the topic. The repository contain the dataset 
(IE. legal_help_clean.csv) used to create the chatbot.

### Data Pre-Processing
Text pre-processing are done using NLTK python package. The input user query is tokenized with the punctuation remove.
Next, Part of Speech (POS) tagging is done before Lemmatization. Lastly, stop word is removed from the user input query. 
The training text are pre-processed in the same way as the user input query to ensure consistency.

### Latent Sematic Indexing (LSI)
LSI (also known as Latent Semantic Analysis, LSA) learns latent topics by performing a matrix decomposition (SVD) on the 
term-document matrix. Singular Value Decomposition (SVD) was used to reduce the dimensions of the document vector to 
find latent relationships between words and improve information understanding. When a user types in a question 
(user-input-question), the user-input question would be pre-processed in the same way and transformed into vectors using the 
SVD reduced corpus-questions TF-IDF term-document matrix. Cosine Similarity was used to find similar corpus-questions to the 
user-input-question by comparing the corpus questions vectors to the user-input-question vector. 
The answer to the most similar corpus-question would be returned to the user.

### Singular Value Decomposition (SVD)
SVD decomposed the TF-IDF vectors into smaller dimensions as follows:-

     A=UDV^T 
     where A is the term-document matrix. 
   
In the process, potential noise in the original corpus-questions could be eliminated and synonyms in the corpus-questions 
could be identified an orthogonal axis. This resulted in a new smaller vector for each corpus-question. 
