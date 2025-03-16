# Qantas Airways Sentiment Analysis

## Project Overview
This project involves web scraping airline reviews for Qantas Airways and performing sentiment analysis using machine learning models. The sentiment analysis model is deployed via a Streamlit web application.

---

## Repository Structure

Sentiment_Analysis_QantasAirways/
│
├── Web scraped data/                   # Contains CSV files with scraped reviews
│   ├── lounge_review_df.csv       
│   ├── review_df.csv               
│   ├── seat_review_df.csv     
|         
├── models/                             # Trained models used for sentiment analysis
│   ├── logistic_regression.pkl                       
│   ├── naive_bayes.pkl                      
│   ├── random_forest.pkl   
|   ├── vectorizer.pkl            
│
├── Sentiment Analysis.ipynb            # Jupyter notebook for preprocessing, training, and evaluation.
├── app.py                              # Streamlit application for sentiment classification.
├── video_demo.mp4                      # Demonstration video of the application.
├── README.md                           # Project overview and instructions
---

## Web Scraping and Data Preprocessing
1. Reviews are scraped from [Airline Quality](https://www.airlinequality.com/airline-reviews/qantas-airways/) using `requests` and `BeautifulSoup`.
2. Data is stored in CSV files and preprocessed:
   - Text cleaning (removing punctuation, numbers, and stopwords).
   - Tokenization and lemmatization.
   - Converting ratings into binary labels:
     - `>= 8` → **Positive (1)**
     - `< 8` → **Negative (0)**
   - Vectorization using TF-IDF.

---

## Machine Learning Models
### Models Used:
- **Logistic Regression**
- **Naive Bayes**
- **Random Forest**

Each model is trained and evaluated using:
- **Train-Test Split:** 80-20 ratio
- **Accuracy, Precision, Recall, F1-score**

Trained models are saved as `.pkl` files in the `models/` directory.

---

## Streamlit Web Application (`app.py`)
### Features:
- Users input airline review text.
- The model predicts whether the sentiment is **Positive** or **Negative**.
- Results are displayed in real-time.

### How to Run the App:
```bash
pip install -r requirements.txt
streamlit run app.py
```

---

## Dependencies
Ensure the following Python libraries are installed:
```bash
pip install pandas numpy matplotlib seaborn requests beautifulsoup4 nltk scikit-learn streamlit xgboost
```

---

## Future Improvements
- Enhance model accuracy with advanced NLP techniques (e.g., BERT, LSTMs).
- Implement a real-time web scraper.
- Deploy the app online (e.g., Streamlit Sharing, AWS, or Heroku).

---

## Author
Developed by **Karsh** as part of an NLP project for sentiment analysis on airline reviews.

