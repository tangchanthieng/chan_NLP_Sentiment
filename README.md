# chan_NLP_Sentiment

# Analytics Techniques and Insights

## Pre-processing Steps
Before conducting the main analysis, the following pre-processing steps were applied:
- Dropped unnecessary rows and columns (e.g., rows with null values).
- Cleaned data by:
  - Lowercasing text.
  - Removing multiple spaces, user IDs, site links, punctuation, duplicates, and digits.
- Compared stemming and lemmatization approaches:
  - **Lemmatization** performed better than stemming, but it altered some words.
  - Kept the original tweets for further analysis.
- Removed common words using the **NLTK** library.

### Insights from Pre-processing
- **Frequency Analysis**: The most and least common words were identified.
- **Word Cloud Visualization**: 
  ![Figure 1. Word Cloud](#)

**Key Insights**:
- Most concerns are about **private health insurance** (`private`, `health`).
- Customers inquire about **membership**, **cost**, and **cover policies** (`member`, `cover`, `send us`, `claim`, `dm`).
- Attention is also given to **insurance services** like **Medicare** and **Amplar (AMP)**.

> Refer to the Google Collab file for details of the pre-processing steps.

## Text Feature Extraction
Text data was transformed into numerical values for further analysis using these techniques:

### Bigrams
- **Bigrams**: Two consecutive words extracted using NLTK's `ngrams` and `word_tokenizer`.
- Visualized as a bar chart displaying the **top 20 bigrams**.
  ![Figure 2. Bi-gram Analysis](#)

**Insights**:
- Focus on **private health** matters and inquiries into **insurance services**.
- Social events such as the **Melbourne Marathon** and mentions of **CEO Craig Drummond**.

### Trigrams
- **Trigrams**: Three consecutive words extracted and visualized similarly.
  ![Figure 3. Tri-gram Analysis](#)

**Insights**:
- Richer information compared to bigrams.
- Topics include **insurance inquiries**, **social events** like Melbourne Marathon Festival, and positive feedback on programs.

### Bag of Words
- Used **CountVectorizer** to:
  - Separate words in the text.
  - Generate a **term-document matrix** with word counts.

### Term Frequency-Inverse Document Frequency (TF-IDF)
TF-IDF evaluates word importance:

- **Term Frequency (TF)**:
  \[ TF = \frac{\text{Number of times a word appears in a tweet}}{\text{Total number of words in the tweet}} \]
- **Inverse Document Frequency (IDF)**:
  \[ IDF = \log\left(\frac{\text{Total number of tweets}}{\text{Number of tweets containing the word}}\right) \]
- **TF-IDF** = TF * IDF

## Temporal Analysis

### Tweet by Date
- Visualized **tweet counts** over time.
  ![Figure 4. Tweet Counts by Date](#)

**Observations**:
- High engagement during:
  - **September 2017**: Over 160 tweets per day.
  - **2019-2021**: Peaks during the COVID-19 pandemic.
- Possible events:
  - Allegations by ACCC (2018).
  - Global health crisis (COVID-19 pandemic).

### Tweet by Time
- Analyzed tweet engagement by **time of day**:
  - **Morning**: 6 AM - 1 PM
  - **Afternoon**: 1 PM - 6 PM
  - **Evening**: 6 PM - Midnight
  - **Nighttime**: Midnight - 6 AM
  ![Figure 5. Tweet Counts by Time](#)

**Insights**:
- **Nighttime** sees the most tweets.
- Mornings and evenings are also active. 
- Recommendation: Schedule posts during high-engagement hours.

## Sentiment Analysis
- Conducted using **TextBlob** to categorize tweets as:
  - Positive ( > 0 )
  - Neutral ( = 0 )
  - Negative ( < 0 )

### Sentiment Distribution
![Figure 6. Sentiment Distribution](#)

**Observations**:
- Most tweets are **positive** and **neutral**.
- Negative sentiment highlights areas for **service improvement**.

### Sentiment by Date
- Time series visualization of **average sentiment over time**.
  ![Figure 7. Sentiment by Date](#)

**Insights**:
- Volatility increased **after 2019**, likely due to:
  - COVID-19 pandemic.
  - ACCC case.
  - Data breach incidents.

### Sentiment by Year
![Figure 8. Sentiment by Year](#)
- Sentiment decreased **significantly** over the years, especially from 2019 onward.

### Sentiment by Month
![Figure 9. Sentiment by Month](#)
- Sentiment fluctuates but shows improvement towards the **end of the year**.
- Recommendation: Address uncertainty in customer satisfaction throughout the year.

## Topic Modelling
- Performed using **LDA (Latent Dirichlet Allocation)**.
- Generated **Top 10 topics** with keywords.

**Examples**:
1. **Topic 1**: Insurance policy.
2. **Topic 2**: Customer inquiries.
3. **Topic 3**: Payment, claim, and cover conditions.

### Example Topic Keywords:
```
0.024*"health" + 0.017*"private" + 0.013*"not" + 0.010*"cover" + 0.009*"amp" + 0.008*"time"
```
**Interpretation**: Private health coverage issues.

```
0.037*"free" + 0.024*"feelgoodprogram" + 0.019*"parkrun" + 0.013*"fitness" + 0.011*"get" + 0.010*"legend"
```
**Interpretation**: Positive feedback on the **parkrun** program.

![Figure 10. Interactive Topic Analyzer](#)

## Conclusions and Recommendations

### Key Findings
- **Word Frequency**: Customers focus on **health insurance** and related services.
- **Sentiment Analysis**: 
  - Sentiment declined after the **data breach** and **pandemic**.
  - Positive feedback on events like the **parkrun** program.
- **Topic Modelling**: Highlighted customer inquiries, feedback, and recurring themes.

### Recommendations
1. **Improve Marketing Strategies**:
   - Address **customer sentiment** decline post-data breach.
   - Use **proactive communication** to ensure transparency.
2. **Enhance Service Quality**:
   - Mitigate **negative sentiment** and build trust.
3. **Leverage Positive Events**:
   - Promote events like the **parkrun** and **marathon festival**.
4. **Invest in Data Analytics**:
   - Monitor external events.
   - Extract actionable insights to respond effectively to trends.

---
