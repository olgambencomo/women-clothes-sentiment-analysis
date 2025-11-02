# 🛍️ Customer Review Analysis

##  Project Overview

This project analyzes customer reviews from a women's clothing e-commerce store to extract sentiment, emotions, and insights.  
It demonstrates a *omplete Python workflow, from data cleaning to sentiment scoring and emotion detection, producing a dataset ready for visualization in dashboards or further analysis.

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.6-green?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NLTK](https://img.shields.io/badge/NLTK-3.8-orange?logo=python&logoColor=white)](https://www.nltk.org/)
[![TextBlob](https://img.shields.io/badge/TextBlob-0.17-yellow?logo=python&logoColor=white)](https://textblob.readthedocs.io/en/dev/)
[![VADER](https://img.shields.io/badge/VADER-sentiment-red)](https://github.com/cjhutto/vaderSentiment)
[![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-purple?logo=transformers&logoColor=white)](https://huggingface.co/docs/transformers/index)
[![NRCLex](https://img.shields.io/badge/NRCLex-0.0.1-pink)](https://pypi.org/project/NRCLex/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-orange?logo=power-bi&logoColor=white)](https://powerbi.microsoft.com/)


## Jupyter Workflow Steps

### 1️⃣ Data Loading
- Imported dataset with `pandas`.
- Explored key columns: `Review Text`, `Rating`, `Age`, `Department Name`, `Class Name`.

### 2️⃣ Data Cleaning
- Dropped unnecessary columns and missing reviews.
- Removed rows missing product metadata (`Division Name`, `Department Name`, `Class Name`) for accurate aggregation.
- Cleaned review text:
  - Lowercase, remove URLs, punctuation, numbers, extra spaces.
  - Tokenization & stopwords removal using NLTK.
- Stored cleaned text in `Clean_Review`.

### 3️⃣ Sentiment Analysis
- **VADER:** Positive, Neutral, Negative, and Compound scores; label assignment.  
- **RoBERTa (Hugging Face):** Sentiment label and confidence score.  
- **TextBlob:** Subjectivity score → `Subjective` vs `Objective`.

### 4️⃣ Emotion Detection
- **NRCLex** to detect all emotions in reviews (`Emotions`).  
- Extracted main emotion as `Primary_Emotion`.

### 5️⃣ Dataset Enrichment & Export
- Final dataset includes:
  - Original columns + `Clean_Review`.
  - Sentiment scores & labels (VADER & RoBERTa).
  - TextBlob subjectivity.
  - Emotions & primary emotion.
- Exported to **Excel**, ready for Power BI dashboards.

---

