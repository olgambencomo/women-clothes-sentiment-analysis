# 🛍️ Customer Review Analysis

##  Project Overview

💡 Goal: Extract insights from customer reviews for better product, marketing, and engagement strategies.  
📊 Tools: Python, NLP, Sentiment Analysis, Emotion Detection, Power BI.

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.6-green?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NLTK](https://img.shields.io/badge/NLTK-3.8-orange?logo=python&logoColor=white)](https://www.nltk.org/)
[![TextBlob](https://img.shields.io/badge/TextBlob-0.17-yellow?logo=python&logoColor=white)](https://textblob.readthedocs.io/en/dev/)
[![VADER](https://img.shields.io/badge/VADER-sentiment-red)](https://github.com/cjhutto/vaderSentiment)
[![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-purple?logo=transformers&logoColor=white)](https://huggingface.co/docs/transformers/index)
[![NRCLex](https://img.shields.io/badge/NRCLex-0.0.1-pink)](https://pypi.org/project/NRCLex/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-orange?logo=power-bi&logoColor=white)](https://powerbi.microsoft.com/)


## Dataset Overview  

The raw dataset includes **23,486 rows** and **10 feature variables**.  
Each row represents a **customer review** from a women's clothing e-commerce platform.  

| Variable | Description |
|-----------|--------------|
| **Clothing ID** | Integer categorical variable that refers to the specific piece being reviewed. |
| **Age** | Positive integer variable of the reviewer’s age. |
| **Title** | String variable for the title of the review. |
| **Review Text** | String variable for the review body. |
| **Rating** | Ordinal integer variable (1 = Worst, 5 = Best) for the product score given by the customer. |
| **Recommended IND** | Binary variable indicating if the customer recommends the product (1 = Yes, 0 = No). |
| **Positive Feedback Count** | Positive integer showing how many customers found this review helpful. |
| **Division Name** | Categorical variable for the product’s high-level division. |
| **Department Name** | Categorical variable for the product’s department. |
| **Class Name** | Categorical variable for the product’s class name. |


## Jupyter Workflow Steps

<details>
<summary>Click to expand</summary>

### 1️⃣ Data Loading
- Imported dataset with `pandas`.
- Explored key columns: `Review Text`, `Rating`, `Age`, `Department Name`, `Class Name`.

### 2️⃣ Data Cleaning
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

</details>

---

## 📊 Power BI Dashboard & Key Insights
<details>
<summary>Click to expand</summary>

The enriched dataset (22,628 reviews) was used to build an interactive Power BI dashboard that visualizes customer sentiment, product performance, and demographic behavior.  
The goal was to evaluate sentiment polarity (positive, neutral, negative) and its coherence with star ratings using two NLP models.

---

###  Model Comparison & Evaluation  

Two sentiment models were compared:  
- VADER: rule-based model focused on lexical sentiment.  
- RoBERTa: transformer-based deep learning model with contextual understanding.  

Both achieved a low average error (0.73–0.74) against actual user ratings, confirming a strong alignment between textual sentiment and numeric feedback.

However, VADER showed a positivity bias, classifying over 95% of reviews as positive, underdetecting neutral or subtle negative tones.  
In contrast, RoBERTa produced a more balanced distribution:
- 81.9% Positive  
- 13.6% Neutral  
- 4.5% Negative  

Because of its higher contextual accuracy and realistic correlation with ratings, RoBERTa was selected as the main model for sentiment analysis.

---

### Overall Customer Satisfaction  

- 81.9% positive reviews and only 4.5% negative → strong brand trust and satisfaction.  
- Average star ratings match sentiment:  
  - Positive →  4.4  
  - Neutral →  3.4  
  - Negative → 2.4  
- Positive reviews are often linked with emotions such as joy, trust, and anticipation.  

---

###  Product & Department Performance  

- Top-performing categories: Dresses, Knits, Jeans, Pants, and Blouses.  
  - These show consistent satisfaction levels and alignment between text and ratings.  
- Trend department shows the lowest performance (avg rating 3.8), signaling potential issues in fashion expectations or sizing.  
- Tops, Bottoms, and Intimate departments maintain high satisfaction (82%+ positive, avg rating 4.3).  
- Popular items like **Dresses and Blouses** generate both praise and criticism — natural polarization for high-volume products.  

 Strategic takeaway: Focus improvement efforts on the Trend department and use highly reviewed products to identify quality or fit issues.

---

### Customer Demographics  

- 35–44 years: most active group (7,400+ reviews).  
- 18–24 years: fewer reviews but high positivity → growth potential via social media and influencer campaigns.  
- Target engaged segments (25–44) for loyalty or ambassador programs.  

---

### Review Objectivity & Subjectivity  

- Positive reviews: 74% subjective — emotional appreciation (“Love it!”, “Perfect fit”).  
- Negative reviews: more objective (40%) — focused on issues like fit, material, or delivery.  
- Categories like Tops and Dresses show more emotional language, ideal for branding campaigns.  

---

### 🔍 Sentiment vs Recommendation  

- Customers who recommend products → 88.95% positive sentiment.  
- Those who don’t recommend → only 50% positive and 19% negative.  
✅ Indicates that **positive emotions directly drive recommendation behavior**.

---

### 💡 Strategic Opportunities  

| Focus Area | Recommendation |
|-------------|----------------|
| **Product Optimization** | Prioritize top-performing categories (Dresses, Blouses, Knits). |
| **Customer Retention** | Build loyalty programs for 25–44 segment. |
| **Reputation Management** | Address objective negative feedback to improve experience. |
| **Emotional Branding** | Use joy & trust themes in marketing campaigns. |
| **Youth Engagement** | Boost 18–24 participation through social media challenges and referral programs. |




</details> 
