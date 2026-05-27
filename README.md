# YouTube Watch History — EDA & Sentiment Analysis

A personal data analysis project built on my own YouTube watch history,
exported via Google Takeout. The project covers exploratory data analysis
followed by a full sentiment analysis pipeline on video titles.

## Dataset

- Source: Google Takeout (`watch-history.json`)
- Contains video titles, channel names, watch timestamps, and URLs
- Categories are derived using keyword-based rule matching on titles

## Project Structure

```
Youtube_EDA_My_History/
├── myyoutubedataanalyze.ipynb   # Main analysis notebook
├── README.md
└── img3/                        # Output visualizations
```

## Part 1 — Exploratory Data Analysis

- Total videos watched and date range of history
- Top 10 most watched channels
- Watching activity by hour of day
- Daily and yearly YouTube usage trends
- Most active days of the week
- Word cloud of video titles
- Content category distribution (AI/ML, History, Politics, Career, Animals, Other)

## Part 2 — Sentiment Analysis

Sentiment analysis was performed on cleaned video titles using two libraries
and a custom emotion lexicon.

### Sentiment Scoring — VADER

VADER (Valence Aware Dictionary and sEntiment Reasoner) assigns each title
a compound score $S \in [-1, +1]$, where:

- $S \geq 0.05$ → Positive
- $S \leq -0.05$ → Negative
- Otherwise → Neutral

### Subjectivity — TextBlob

TextBlob was used to measure how opinion-based vs factual each title is,
returning a subjectivity score in $[0, 1]$.

### Emotion Detection — Custom Lexicon

Since NRCLex had environment compatibility issues on Kaggle, a custom
keyword-based emotion lexicon was built covering 8 emotions:
fear, anger, joy, sadness, disgust, surprise, trust, and anticipation.

### Visualizations

- Sentiment distribution (pie chart + compound score histogram)
- Emotion frequency bar chart across all titles
- Monthly sentiment trend over time
- Category-wise average sentiment (horizontal bar)
- Top 10 channel sentiment comparison
- Emotion heatmap by content category
- Polarity vs subjectivity scatter plot

## Libraries Used

```
pandas, numpy, matplotlib, seaborn,
vaderSentiment, textblob, wordcloud, scikit-learn
```

## How to Run

1. Export your YouTube history from [Google Takeout](https://takeout.google.com)
2. Upload `watch-history.json` as a Kaggle dataset
3. Run all cells in `myyoutubedataanalyze.ipynb` sequentially

## Author

Aditya Majumder
[Kaggle](https://www.kaggle.com/adityamaj20051004) · [GitHub](https://github.com/aditya20051004)
