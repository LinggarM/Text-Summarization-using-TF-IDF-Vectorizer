# Text-Summarization-using-TF-IDF-Vectorizer
Simple Text Summarization using **TF-IDF Vectorizer** and **NLTK** library

## About the Project

This project focuses on utilizing the **Term Frequency-Inverse Document Frequency (TF-IDF)** technique for text summarization. The goal is to automatically generate concise and meaningful summaries from longer texts, such as articles, documents, or any body of text.

**Key Features:**
 - TF-IDF Vectorization: The project leverages TF-IDF vectorization to represent each sentence in the text as a numerical vector, capturing the importance of each term in the context of the entire document.
 - Sentence Scoring: Each sentence is scored based on its TF-IDF representation, allowing for the identification of key sentences that contribute significantly to the overall content.
 - Threshold-based Summarization: A threshold is defined to select the most important sentences for the final summary. Sentences with TF-IDF scores equal to or greater than the threshold are included in the summarized output.

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

1. Install the dependencies
   ```sh
   pip install -r requirements.txt
   ```
2. Open notebook file in [notebooks/text_summarization.ipynb](notebooks/text_summarization.ipynb)
3. Input the document by copy-paste your document (articles, news, essays, etc) into `sentence` variable
4. Run all the cells
5. The final summary will be saved in the `final_summ` variable and can be viewed in the `Summarization Result` section.

## Contributors
* [Linggar Maretva Cendani](https://github.com/LinggarM) - [linggarmc@gmail.com](mailto:linggarmc@gmail.com)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
