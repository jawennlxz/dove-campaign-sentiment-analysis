# Dove Campaign Sentiment Analysis

Compares how audiences responded to two Dove campaign videos, **Reverse Selfie** and **Dove Evolution**, by running sentiment analysis on their YouTube comments with VADER.

Module: CET365 Social Media Metrics and Analytics, Singapore University of Social Sciences (2025). Group project; this repository contains the data preparation and sentiment analysis code.

> **Disclaimer:** This is an academic project completed for coursework. It is not affiliated with, endorsed by or commissioned by Dove or Unilever. The analysis uses a sample of public comments provided for coursework, and the findings do not represent Dove's own data or views.

## Approach

1. **Filter** the comment dataset to the two campaign videos.
2. **Remove non-English or corrupted comments** using `langdetect`, as they add noise and can skew results.
3. **Light cleaning for VADER.** Only URLs are removed. Stopwords, punctuation, emojis and capital letters are kept on purpose, because VADER uses them to judge the strength of a sentiment (for example, "GREAT!!!" scores higher than "great").
4. **Classify sentiment** from VADER's compound score: above 0.1 is positive, below -0.1 is negative, and anything in between is neutral.
5. **Visualise** the sentiment counts for each video as bar charts.

## Results

| Video | Positive | Neutral | Negative |
|---|---|---|---|
| Reverse Selfie | 293 | 69 | 70 |
| Dove Evolution | 1,704 | 589 | 646 |

- Both campaigns were received positively overall.
- Dove Evolution drew nearly 7 times more comments, with more of both positive and negative reactions, which points to a more provocative message that sparked stronger discussion.
- Reverse Selfie had a more balanced spread, in line with a subtler message.

## How to run

```bash
pip install pandas langdetect vaderSentiment matplotlib jupyter
jupyter notebook dove_sentiment_analysis.ipynb
```

The notebook expects a file named `dove_commercial_comments.csv` with the columns `video_id`, `video_title` and `comment`. The dataset was provided for coursework and is not included here.

## Skills demonstrated

- Sentiment analysis with VADER
- Language detection and data cleaning with pandas
- Data visualisation with matplotlib
- Turning sentiment results into campaign insights

## Author

Jawenn Lim
