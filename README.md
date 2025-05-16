# Sentiment Analysis of User Communications

## Overview

This project analyzes the sentiment of user email communications to identify patterns of positivity and negativity across employees. The analysis uses average and weighted sentiment scores to highlight key contributors and flags users for potential intervention based on their negative sentiment trends.

---

## Top Users by Sentiment

### Top 3 Positive Users (by Average Sentiment)
| Rank | User Email               | Avg Sentiment Score |
|-------|-------------------------|---------------------|
| 1     | johnny.palmer@enron.com | 0.276995            |
| 2     | eric.bass@enron.com     | 0.257143            |
| 3     | lydia.delgado@enron.com | 0.228873            |

### Top 3 Negative Users (by Average Sentiment)
| Rank | User Email              | Avg Sentiment Score |
|-------|------------------------|---------------------|
| 1     | don.baughman@enron.com | 0.159624            |
| 2     | rhonda.denton@enron.com| 0.162791            |
| 3     | patti.thompson@enron.com| 0.186667           |

### Top 3 Positive Users (by Weighted Sentiment Score)
> Weighted score accounts for message volume, reducing noise from outliers.
| Rank | User Email               | Weighted Score |
|-------|-------------------------|----------------|
| 1     | lydia.delgado@enron.com | 65.0           |
| 2     | johnny.palmer@enron.com | 59.0           |
| 3     | eric.bass@enron.com     | 54.0           |

### Top 3 Negative Users (by Weighted Sentiment Score)
| Rank | User Email               | Weighted Score |
|-------|-------------------------|----------------|
| 1     | rhonda.denton@enron.com | 28.0           |
| 2     | don.baughman@enron.com  | 34.0           |
| 3     | kayne.coulter@enron.com | 36.0           |

> **Note:** Lydia Delgado's consistent positivity and high message volume place her at the top for positive weighted scores. Users with fewer messages but high average sentiment are ranked lower, which helps reduce noise. Similarly, negative weighted scores highlight active users with moderately negative sentiment over those with fewer, highly negative messages.

---

## Flagged Users for Negative Sentiment  
Based on a 30-day rolling window of messages with high negative sentiment scores:
- john.arnold@enron.com  
- don.baughman@enron.com  
- sally.beck@enron.com  

---

## Key Insights

- Approximately 66% of messages are **Neutral**, 27% **Positive**, and 6% **Negative**, indicating an imbalanced sentiment distribution that could impact model performance.
- Weighted sentiment metrics highlight users who consistently influence overall organizational sentiment.
- Monthly sentiment fluctuations suggest correlations with company events affecting employee mood and engagement.
- Negative sentiment rolling window analysis helps identify users potentially needing support or management attention.
- Text length and vocabulary size metrics provide additional context on communication styles, useful for refining sentiment models.

---

## Recommendations

- Apply techniques such as **SMOTE**, **class weighting**, or **focal loss** during model training to improve classification of minority classes, especially Negative sentiment.
- Implement automated monitoring and alerts for users flagged due to frequent negative communications to provide timely support.
- Use weighted sentiment analysis to prioritize sentiment-driven interventions and recognize influential communicators.
- Investigate users with mixed positive and negative sentiment patterns to better understand nuanced communication styles.
- Experiment with n-gram features, advanced embedding models, and domain-specific stopword lists to enhance model accuracy and robustness.

---

*This analysis supports data-driven organizational health monitoring and targeted employee engagement strategies.*
