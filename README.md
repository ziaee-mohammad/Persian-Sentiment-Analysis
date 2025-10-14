# 🇮🇷 Persian Sentiment Analysis

An end‑to‑end **NLP** project for classifying **Persian (Farsi)** text into **positive / negative / neutral**.  
Includes Persian‑specific preprocessing (normalization, ZWNJ handling, digit/character unification), feature extraction (**TF‑IDF / embeddings**), classical ML baselines (Logistic Regression, Linear SVM, Naive Bayes), and optional **Transformer** models (ParsBERT / mBERT / XLM‑R).

---

## 📖 Overview
This repository implements a reproducible sentiment pipeline tailored to **Persian**:
- Text cleaning & normalization (**Arabic→Persian char map**, digits, diacritics)  
- Tokenization, stopword removal, **lemmatization** (Hazm/Parsivar)  
- Feature extraction with **TF‑IDF** (1–2/1–3 n‑grams) or **Transformer embeddings**  
- Model training & tuning (LogReg, SVM, NB; optional ParsBERT fine‑tuning)  
- Evaluation with **Accuracy, F1‑macro**, confusion matrix, and error analysis

---

## 🗂️ Dataset
Expected CSV layout under `Dataset/`:
```
Dataset/
├─ train.csv
└─ test.csv
```
**Columns (examples):**
- `text` — Persian sentence/review/post  
- `label` — `pos` / `neg` / `neu` (or `1/0` for binary)

> You can adapt to public Persian datasets (e.g., review datasets, SentiPers‑style formats). Ensure you cite the source you use.

---

## 🧹 Persian‑Specific Preprocessing
- **Normalization**: convert Arabic `ي/ك` → Persian `ی/ک`; unify digits; remove diacritics; trim extra spaces  
- **ZWNJ** (نیم‌فاصله): normalize half‑spaces; optionally remove for TF‑IDF
- **URLs / mentions / hashtags**: strip or normalize (keep hashtag text)  
- **Tokenization & Lemmatization**: via **Hazm** (or Parsivar)  
- **Stopwords**: Persian stoplist (Hazm); extend with domain‑specific words
- **Optional**: emoji mapping to sentiment tokens

---

## 🧠 Models
- **Logistic Regression** — strong linear baseline on TF‑IDF  
- **Linear SVM** — often top classical model with sparse features  
- **Multinomial Naive Bayes** — fast baseline  
- **(Optional)** Transformers: **ParsBERT** (`HooshvareLab/bert-fa-base-uncased`), **mBERT**, **XLM‑R**

---

## 📈 Evaluation (replace with your numbers)
| Model | Accuracy | F1‑macro |
|------|---------:|---------:|
| Logistic Regression (TF‑IDF) | 0.90 | 0.89 |
| Linear SVM (TF‑IDF)         | 0.92 | 0.91 |
| Naive Bayes (TF‑IDF)        | 0.88 | 0.86 |
| ParsBERT (fine‑tuned)       | 0.94 | 0.93 |

Export:
- Confusion matrix (3‑class)  
- Per‑class precision/recall/F1  
- Top informative n‑grams (for linear models)

---

## 🧩 Repository Structure (suggested)
```
Persian-Sentiment-Analysis/
├─ Dataset/                        # train/test CSVs
├─ Notebook/
│  └─ Persian_Sentiment.ipynb      # main analysis notebook
├─ src/                            # optional scripts
│  ├─ normalize_fa.py              # Persian normalizer (char map, ZWNJ, digits)
│  ├─ data.py                      # loading/cleaning
│  ├─ features.py                  # TF-IDF / embeddings
│  ├─ train.py                     # training & tuning
│  └─ eval.py                      # metrics & plots
├─ reports/figures/                # CM, PR, feature plots
├─ requirements.txt
├─ .gitignore
└─ README.md
```

---

## ⚙️ Setup & Usage
1) **Clone & install**
```bash
git clone https://github.com/ziaee-mohammad/Persian-Sentiment-Analysis.git
cd Persian-Sentiment-Analysis
pip install -r requirements.txt
```

2) **Run notebook**
```bash
jupyter notebook Notebook/Persian_Sentiment.ipynb
```

3) **(Optional) Run scripts**
```bash
python -m src.train --model "svm" --ngrams 1,2 --max_features 200000
python -m src.eval  --report
```

---

## 📦 Requirements (example)
```
pandas
numpy
scikit-learn
hazm
parsivar
nltk
matplotlib
seaborn
```
> For Transformers: add `torch` and `transformers`.

---

## ✅ Good Practices
- Use **stratified** split to preserve class ratios  
- Keep vectorizer + model in a single `Pipeline` to avoid leakage  
- Fix random seeds for reproducibility  
- Save vectorizer/model artifacts for deployment  
- Document your normalization choices (e.g., ZWNJ handling)

---

## 🏷 Tags
```
data-science
machine-learning
nlp
sentiment-analysis
persian
farsi
text-mining
classification
tf-idf
scikit-learn
```

---

## 👤 Author
**Mohammad Ziaee** — Computer Engineer | AI & Data Science  
📧 moha2012zia@gmail.com  
🔗 https://github.com/ziaee-mohammad

---

## 📜 License
MIT — free to use and adapt with attribution.
