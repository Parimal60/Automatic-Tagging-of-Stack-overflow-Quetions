# Automatic-Tagging-of-Stack-overflow-Quetions

1) Original data has aroung 12,00,000 Questions and 37,000 unique tags. 
2) Removed the Questions having score < 5, and took only 100 most frequent tags, questions having no common tags also removed. Reducing the data size to around 62k Questions and 100 tags
3) Text processing steps : 1) Converted HTML tags to text body 2) Cleaning the text i.e, replacing commonly used shortcut words with complete word 3) Removing the punctuation except 'C#" etc 4) Removing the stopwords 5) Performing lemmatization 
4) This is a Multi-label classification problem, so transformed target tags (y) into binary multi-label targets of dimension 100 
5) Used different types of features for performing classification. a) TF_IDF feautes only b) tf-idf weighted Glove embeddings with dimension 300 and 100 both c) Using pre-trained tf-idf weighted Word2Vec 300-dim embeddings d) Trained Word2Vec model on text corpus and used it with tf-idf weights 
