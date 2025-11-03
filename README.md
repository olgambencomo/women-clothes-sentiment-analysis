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

The enriched dataset was used to create an interactive Power BI dashboard. Key insights include:

###  Overall Customer Satisfaction
- 81.9% positive reviews, 4.5% negative → strong trust and satisfaction.  
- Average star ratings align with sentiment:
  - Positive → 4.4 stars  
  - Neutral → 3.4 stars  
  - Negative → 2.4 stars  
- Positive reviews are linked to joy, trust, and anticipation.

### Product Performance
- Dresses → top category (27% of reviews) with highest positive feedback.  
- Other strong categories: knits, blouses, sweaters.  
- Low-engagement: shorts, outerwear, lounge items (<2%).  
- Strategy: Promote cross-selling to increase visibility of low-engagement categories.

###  Customer Demographics
- 35–44 years → most active (7,400+ reviews).  
- 18–24 → fewer reviews but high positivity → growth opportunity via social media campaigns.  
- Engage highly active age groups with loyalty or ambassador programs.

### Sentiment vs. Recommendation
- Recommenders → 88.95% positive sentiment  
- Non-recommenders → 50% positive, 19% negative  
- Insight: Positive emotions strongly drive recommendations.

### Nature of Reviews
- Positive → mostly subjective (74%), expressing personal appreciation.  
- Negative → more objective (40%), focused on fit, material, delivery.  


###  Strategic Opportunities
- Product Optimization: Focus on top categories.  
- Customer Retention: Loyalty programs for 25–44 age segment.  
- Reputation Management: Address objective negative feedback.  
- Emotional Branding: Leverage joy and trust in campaigns.  
- Youth Engagement: Encourage 18–24 participation via social media and referral programs.

---

###  Final Takeaways
- Strong brand reputation and high customer satisfaction.  
- Loyal customer base confirmed by sentiment, ratings, and recommendations.  
- Opportunities exist to address negative feedback and expand reach to younger audiences.

</details> 
