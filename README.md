# 🧠 Persian Sentiment Analysis (SnappFood)

A Flask-based web application for classifying *Persian (Farsi)* user reviews as either *positive 🙂* or *negative 🙁*.  
This project uses *Hazm* for Persian text preprocessing and *XGBoost* for machine learning–based sentiment classification.

---

## 🚀 Features

- Preprocesses Persian text using:
  - Normalization  
  - Tokenization  
  - Stemming & Lemmatization (via Hazm)
- Machine Learning model trained with *XGBoost*
- Web interface built using *Flask*
- Interactive form for users to enter and analyze reviews
- Fully local execution — no external API required

---

## 🧩 Project Structur
📂 Persian-Sentiment-Analysis/
 ┣ 📜 app-mziaee.py — Main Flask app
 ┣ 📂 templates/ — HTML templates for the web UI
 ┣ 📂 static/ — Static assets (CSS, JS, images)
 ┣ 📜 vectorizer.pkl — Text vectorizer
 ┣ 📜 xgb.pkl — Trained XGBoost model
 ┣ 📜 Sentiment_Analysis_of_Snappfood_Comments_by_MZiaee.ipynb — Notebook (preprocessing & training)
 ┗ 📜 README.md — Project documentation

🧠 Model Info

Algorithm: XGBoost

Language Processing: Hazm (for stemming, lemmatization, and normalization)

Dataset: SnappFood customer reviews (preprocessed and labeled manually)



---

👨‍💻 Author

Developed by Mohammad Ziaee
📧 moha2012zia@gmail.com
