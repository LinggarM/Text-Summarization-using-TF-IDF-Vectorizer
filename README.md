# Text-Summarization-using-TF-IDF-Vectorizer
Text Summarization using TF-IDF Vectorizer

Movie Synopsis Text Clustering using **K-Means Clustering** and **TF-IDF Vectorizer** and deployment using framework **Flask**.

## About the Project

This project is a major assignment project for the second semester of the **natural language processing** course. The objective of this task is to collect movie synopsis data, perform text clustering on the movie synopsis data into k amount of clusters, and transform it into a web application.

In this project, we use **K-Means Clustering** to perform text clustering and **TF-IDF Vectorizer** as Word Embedding (to convert text data into vectors).

## Technology Used

  * Python
  * Scikit-learn
  * NLTK (Natural Language Toolkit)

## Notebook File
* [notebooks/text_summarization.ipynb](notebooks/text_summarization.ipynb)

## Workflow

### Data Collection
  - The input data for this project is a long text consisting of a **group of sentences**. It could be articles, news, blog posts, essays, etc. This text will then be summarized by utilizing the **TF-IDF Vectorizer**.

### Data Preprocessing
  The data preprocessing steps applied to the data include:
  - **Sentence tokenization** using **NLTK** library: Breaking the text into separate sentences.
  - **Stopwords removal** using **TF-IDF Vectorizer** model
  - Train the **TF-IDF Vectorizer** model.

### Calculate Sentence Score
  - Each sentence that has been transformed into vector representation using **TF-IDF Vectorizer** is then scored by summing the TF-IDF values of each word in the sentence and dividing it by the total number of words in that sentence (Calculating **the average TF-IDF score**).
  - Each sentence will then have its own TF-IDF score, which will be utilized in the subsequent stages.  

### Define Threshold & Get Sentences
  - To obtain a summary of the long input text, we will select some main sentences and discard other less important sentences, resulting in a shorter summary than the original input document. The summary will contain the most important sentences that best represent the document.
  - The method for obtaining these key sentences is by **selecting the top n sentences with the highest TF-IDF scores**. In this project, we use a **threshold value**, obtained by averaging the TF-IDF scores of all sentences (sum of TF-IDF score of all sentences/ total number of sentences). Then, all sentences with TF-IDF scores greater than or equal to the threshold value will be chosen to be included in the **final summary**.

## Usage (Tutorials)

1. Open notebook file in [notebooks/text_summarization.ipynb](notebooks/text_summarization.ipynb)
2. Input the document by copy-paste your document (articles, news, essays, etc) into `sentence` variable
3. Run all the cells
4. The final summary will be saved in the `final_summ` variable and can be viewed in the `Summarization Result` section.

## Contributors
* [Linggar Maretva Cendani](https://github.com/LinggarM) - [linggarmc@gmail.com](mailto:linggarmc@gmail.com)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
