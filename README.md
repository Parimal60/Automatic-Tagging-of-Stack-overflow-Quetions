# Automatic-Tagging-of-Stack-overflow-Quetions

1) Original data has around 12,00,000 Questions and 37,000 unique tags. 
2) Removed the Questions having score < 5, and took only 100 most frequent tags, questions having no common tags are also removed. Reducing the final data size to around 62k Questions and 100 tags 
3) Text processing steps : 1) Converted HTML tags to text body 2) Expand Contractions (like "ain't" to "is not”) 3) Converting all text to lower case 4) Removing the punctuation except 'C#" etc 5) Removing the stopwords 6) Performing lemmatization 
4) This is a Multi-label classification problem, so transformed target tags (y) into binary multi-label targets of dimension 100 
5) Used different types of features for performing classification. a) TF_IDF features (1000-dim) b) tf-idf weighted Glove embeddings with dimension of 300 and 100 both c) Using pre-trained tf-idf weighted Word2Vec 300-dim embeddings d) Trained Word2Vec model on text corpus and used it with tf-idf weights  
6) After performing experiments, found that only using tf-idf features is giving the best performace and also is the fastest. 
7) One reason that weighted word embeddings are not performing well can be that, we are almost averaging all word embeddings to get a embedding for a text sentence which can cause a lot of information loss. 
  
