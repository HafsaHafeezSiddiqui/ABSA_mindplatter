# Aspect-Based Sentiment Analysis (ABSA) on "Mind Platter"

## Overview
This project leverages Aspect-Based Sentiment Analysis (ABSA), a subset of Natural Language Processing (NLP), to analyze sentiments and extract key aspects from the book *Mind Platter* by Najwa Zebian. The goal is to identify specific aspects within the text and determine the associated sentiments, providing insights into the author's emotions and themes.

---

## Dataset

- **Source**: *Mind Platter* by Najwa Zebian
- **Data**: Contains 15 chapters of text, each represented with its title and corresponding content.
- **Structure**: Loaded into a Pandas DataFrame with two columns:
  - `Title`: Chapter titles.
  - `Text`: Chapter content.

---

## Methodology

### 1. Preprocessing
The text is preprocessed to prepare for ABSA by:
- Tokenizing the text.
- Removing abbreviations, punctuations, and stopwords.
- Converting text to lowercase.
- Enclosing tokens in quotes for proper formatting.

### 2. Aspect Extraction
Key aspects are identified using:
- **POS Tagging**: Assigns grammatical categories to words (e.g., nouns, verbs).
- **Dependency Parsing**: Analyzes grammatical structures to identify relationships.
- **Pattern Matching**: Uses linguistic patterns like adjective-noun and verb-adverb combinations.

### 3. Sentiment Analysis
- **Tool**: VADER Sentiment Analysis.
- **Polarity**: Classifies sentiments as positive, negative, or neutral based on compound scores.

### 4. Model Development
#### Multinomial Naïve Bayes (MNB) Classifier:
- Used for sentiment classification.
- Features extracted using TF-IDF.
- Model trained and tested with an 80%-20% data split.

#### Performance:
- **Individual Chapters**: 84% accuracy.
- **Chapters as a Whole**: 66.7% accuracy.

---

## Features

1. **Aspect-Based Analysis**:
   - Extracts specific aspects and their associated sentiments.
   - Visualizes sentiment dynamics across chapters.

2. **Holistic Sentiment Analysis**:
   - Aggregates sentiment polarity for entire chapters.

3. **Comprehensive Evaluation**:
   - Benchmarks performance of MNB classifier on granular and holistic data.

---

## Results

- **Accuracy**:
  - Chapters Individually: 84%.
  - Chapters as a Whole: 66.7%.
- **Findings**:
  - Better performance when analyzing chapters individually.
  - Highlighted sentiments (positive, negative, neutral) for extracted aspects.

---

## Installation and Usage

### Requirements
- Python 3.x
- Pandas
- Scikit-learn
- SpaCy
- VADER Sentiment Analysis
- NLTK

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/mind-platter-absa.git
   cd mind-platter-absa
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Preprocess the data:
   ```python
   from preprocessing import preprocess_text
   df['text'] = df['text'].apply(preprocess_text)
   ```
4. Extract aspects:
   ```python
   from aspect_extraction import extract_aspects
   aspects = extract_aspects(df['text'])
   ```
5. Perform sentiment analysis:
   ```python
   from sentiment_analysis import absa
   results = absa(df['text'])
   ```
6. Train the MNB model:
   ```python
   from model_training import train_model
   accuracy = train_model(aspects, sentiments)
   print(f"Model Accuracy: {accuracy}%")
   ```

---

## Contributors
- **Muneeza Iftikhar** (02-136212-012)
- **Hafsa Hafeez Siddiqui** (02-136212-026)
- **Aqsa Khan** (02-136212-039)

---

## Acknowledgements
- **Salas Akbar**, Instructor, Natural Language Processing (CSC-441), Bahria University Karachi Campus.
