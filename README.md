# Text-Summarization-using-TF-IDF-Vectorizer
Simple Text Summarization using **TF-IDF Vectorizer** and **NLTK** library

## About the Project

This project focuses on utilizing the **Term Frequency-Inverse Document Frequency (TF-IDF)** technique and the use of the **NLTK** library  for text summarization. The goal is to automatically generate concise and meaningful summaries from longer texts, such as articles, documents, or any body of text.

**Key Features:**
 - **TF-IDF Vectorization**: The project leverages TF-IDF vectorization to represent each sentence in the text as a numerical vector, capturing the importance of each term in the context of the entire document.
 - **Sentence Scoring**: Each sentence is scored based on its TF-IDF representation, allowing for the identification of key sentences that contribute significantly to the overall content.
 - **Threshold-based Summarization**: A threshold is defined to select the most important sentences for the final summary. Sentences with TF-IDF scores equal to or greater than the threshold are included in the summarized output.

## Technology Used

  * Python
  * Scikit-learn
  * NLTK (Natural Language Toolkit)

## Notebook File
* [notebooks/text_summarization.ipynb](notebooks/text_summarization.ipynb)

## Workflow

### Data Collection
  - The input data for this project is a long text consisting of a **group of sentences**. It could be articles, news, blog posts, essays, etc. This text will then be summarized by utilizing the **TF-IDF Vectorizer**.
  - Example input used in this project:
    <details>
    <summary>Open:</summary>
    Manchester City makes history by winning Club World Cup
    
    Manchester City capped off its incredible year with yet another trophy, dismantling Fluminense 4-0 to win the Club World Cup on Friday.
    
    Having already won the Premier League, Champions League, FA Cup and Super Cup, Pep Guardiola’s side now boasts five trophies this calendar year, becoming the first English club to ever hold all those titles simultaneously.
    
    The final piece of the jigsaw came on a highly charged night in Saudi Arabia as Manchester City outclassed its Brazilian opponents.
    
    “We’ve shown over the past 12 months we are the best team in the world. Our results prove that and the consistency we have managed has been amazing,” club captain Kyle Walker said after the game, per Sky Sports.
    
    “To win these five trophies – for me, the five biggest prizes available to us – is incredible. I am so proud to have been a part of this and I can honestly say it’s an honour to play alongside these players. I couldn’t ask for better teammates.”
    
    It took just 40 seconds for Manchester City to take the lead.
    
    Brazilian left-back Marcelo miscued a pass in the opening exchanges which let Nathan Aké free to shoot from distance. The defender’s effort cannoned back off the post but forward Julián Álvarez was in the right place to turn the rebound into the net with his chest.
    
    City continued to look dangerous and doubled its lead before the break after Phil Foden’s attempted cross was deflected into his own net by Fluminense defender Nino.
    
    Foden then got on the scoresheet himself in the 72nd minute after a prodding home from close range.
    
    The rout was completed in the 88th minute when Álvarez capped off a brilliant performance with a clinical finish into the far corner.
    
    City’s defence was largely untested for during the game, underlining the team’s dominance during this unforgettable year.
    
    “As a manager it is what I am most proud of; that we are always there. No matter how much we win, no matter what trophies we lift, we are there again to fight for the next one,” City boss Guardiola said after the match, according to Sky Sports.
    
    “To win the Treble was truly special, but to win two more trophies and now hold these five major titles shows the unique mentality of this team, of the Club and its fans.
    
    “It is something no other English team has ever achieved, and we will always remember this incredible time we spent together.”
    
    The game ended in some unsavoury scenes as a scuffle broke out between players on the pitch after the final whistle, but the game will be remembered as yet another successful night for City.
    
    The champion heads back to England where it faces a tough title defence in the Premier League.
    
    It currently sits fourth in the table and will face Everton in its next fixture on Wednesday.
  </details> 

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
  - Example final summary:
    <details>
    <summary>Open:</summary>
    “We’ve shown over the past 12 months we are the best team in the world. “To win these five trophies – for me, the five biggest prizes available to us – is incredible. I am so proud to have been a part of this and I can honestly say it’s an honour to play alongside these players. Foden then got on the scoresheet himself in the 72nd minute after a prodding home from close range. “As a manager it is what I am most proud of; that we are always there. The champion heads back to England where it faces a tough title defence in the Premier League. It currently sits fourth in the table and will face Everton in its next fixture on Wednesday.
    </details>

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
