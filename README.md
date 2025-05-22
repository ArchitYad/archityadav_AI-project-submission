# Sentiment Analysis of User Communications

## Overview

This project analyzes the sentiment of user email communications to identify patterns of positivity and negativity across employees. The analysis uses average and weighted sentiment scores to highlight key contributors and flags users for potential intervention based on their negative sentiment trends.

---

## Top Users by Sentiment

### Top 3 Positive Users - Comparison

| Rank | User                      | Log Weighted Score | Bayesian Weighted Score |
|------|---------------------------|----------------------|-------------------------|
| 1    | johnny.palmer@enron.com   | 1.497813             | 1.911270                |
| 2    | eric.bass@enron.com       | 1.376192             | 1.590411                |
| 3    | lydia.delgado@enron.com   | 1.301255             | -                       |
| -    | sally.beck@enron.com      | -                    | 1.623773                |

### Top 3 Negative Users - Comparison

| Rank | User                      | Log Weighted Score | Bayesian Weighted Score |
|------|---------------------------|----------------------|-------------------------|
| 1    | rhonda.denton@enron.com   | 0.842865             | 0.267789                |
| 2    | don.baughman@enron.com    | 0.856541             | -                       |
| 3    | patti.thompson@enron.com  | 1.011833             | 0.334306                |
| -    | lydia.delgado@enron.com   | -                    | 0.258418                |

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
- The rule-based approach identifies employees at risk by looking for patterns of four or more negative messages within a 30-day window, focusing on detecting sudden increases in negativity. Bayesian analysis, on the other hand, estimates the probability of negative behavior, smoothing out short-term fluctuations to identify employees with a more consistent, long-term risk of negative sentiment. The weighted score, calculated using the logarithm of message count, weighs the frequency of negative messages by the overall volume of communication, emphasizing the overall trend of negativity.
-The Bayesian weighted negative score highlights users with a chronic and consistent pattern of negative messaging. The beta distribution's posterior mean method provides the probability of negativity for each user, even those with low message volume but high negative ratios.
-The coefficients from the predictive model are generally very small, indicating weak linear relationships between the past communication features and future sentiment. Notably, the average past sentiment score has the most negative impact on predicted future sentiment, although this effect is also minimal, suggesting that none of the individual or combined features strongly predict future sentiment in a linear fashion.
-Analysis of word frequencies reveals the dominance of stop words like "the," "to," and "and," which carry little semantic meaning. If these were not removed, their removal could be beneficial for tasks like topic modeling. High occurrences of personal pronouns such as "you," "i," and "we," along with words like "please," suggest the data originates from conversational or instructional text, possibly email or chat, with a degree of politeness or formality. Modal and future tense words like "will," "have," and "be" are common, potentially indicating promises, resolutions, or requests, aligning with support tickets or customer communication. The frequent use of "please" suggests a communication style that is often request-heavy or customer-service oriented.
-The prevalence of words like "email," "attached," "file," "number," "contact," "office," "schedule," "meeting," "call," and "phone" strongly indicates that the dataset likely consists of email or support communication, possibly from a corporate environment like the Enron dataset. The frequent use of words such as "thank," "please," "hope," and "help" points to a polite and professional tone, typical of business or customer emails. Time-related words like "day," "week," "time," and specific days of the week suggest discussions involving scheduling or time-sensitive matters. Words such as "know," "need," "see," "question," and "request" indicate an information-seeking tone. Finally, terms like "website," "click," "link," "attached," "file," "email," and "number" suggest a digital or technical context for the communication.

---

## Recommendations

- Apply techniques such as **SMOTE**, **class weighting**, or **focal loss** during model training to improve classification of minority classes, especially Negative sentiment.
- Implement automated monitoring and alerts for users flagged due to frequent negative communications to provide timely support.
- Use weighted sentiment analysis to prioritize sentiment-driven interventions and recognize influential communicators.
-  Use Bayesian Analysis for estimating probability of negative behavior, smoothing noise over time
- Investigate users with mixed positive and negative sentiment patterns to better understand nuanced communication styles.
- Experiment with n-gram features, advanced embedding models, and domain-specific stopword lists to enhance model accuracy and robustness.
- For Feature Engineering, consider enriching the predictive model by incorporating additional features such as rolling averages of sentiment over time, the overall volume of communication from each employee, and Natural Language Processing derived features like topics discussed or shifts in sentiment within a conversation.
-Regarding Model Complexity, exploring more sophisticated algorithms beyond linear regression, such as Random Forest or XGBoost, could allow the model to capture non-linear relationships in the data more effectively. Additionally, using regularized regression techniques like Lasso or Ridge can help prevent the model from overfitting to the training data.
-Specifically for Sentiment Classification tasks, a note on stop words is given: remove them if the focus is primarily on emotionally charged terms, but retain them if aspects like politeness or communication style are relevant to the sentiment being analyzed.
-A Class Imbalance Warning highlights that negative sentiment is underrepresented in the data, which likely leads to the model being less proficient at identifying negative examples. Techniques like data augmentation or class rebalancing (e.g., SMOTE, upsampling) are suggested to mitigate this.
-Finally, concerning Thresholding or Confidence Filtering, if the model's predictions are used in downstream applications, it's advisable to set a confidence threshold. Predictions falling below this threshold could be flagged for manual review or filtered out entirely in sensitive contexts to avoid acting on uncertain classifications.

---

*This analysis supports data-driven organizational health monitoring and targeted employee engagement strategies.*
