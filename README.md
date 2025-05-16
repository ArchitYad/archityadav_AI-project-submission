# archityadav_AI-project-submission
# Sentiment Analysis of User
Top 3 Positive Users (by average sentiment):
                      from  sentiment_score
4  johnny.palmer@enron.com         0.276995
2      eric.bass@enron.com         0.257143
6  lydia.delgado@enron.com         0.228873

Top 3 Negative Users (by average sentiment):
                       from  sentiment_score
1    don.baughman@enron.com         0.159624
8   rhonda.denton@enron.com         0.162791
7  patti.thompson@enron.com         0.186667
Weighted Average Method.
Top 3 Positive Users (weighted):
                      from  weighted_score
6  lydia.delgado@enron.com            65.0
4  johnny.palmer@enron.com            59.0
2      eric.bass@enron.com            54.0

Top 3 Negative Users (weighted):
                      from  weighted_score
8  rhonda.denton@enron.com            28.0
1   don.baughman@enron.com            34.0
5  kayne.coulter@enron.com            36.0

lydia.delgado@enron.com jumps to the top for positive users by weighted score, meaning she’s consistently positive and active. Some users who had a decent average sentiment but low message counts are ranked lower in weighted score (or don’t show up in top 3), which reduces noise from outliers. For negative users, you see a similar pattern — those with more messages but moderately negative sentiment surface higher than those with fewer very negative messages.

# Flagged User 
It is based on negative sentiment on average window size of 30 days having sentiment score near to 4.
       Employee_Email
0   john.arnold@enron.com
1  don.baughman@enron.com
2    sally.beck@enron.com

# Key insights
Majority of messages (~66%) are Neutral, with Positive (~27%) and Negative (~6%) being minority classes. This imbalance may affect model performance and analysis outcomes.
Users with higher message volumes and consistent sentiment stand out more clearly with weighted methods.
Analyzing sentiment by month shows fluctuations in employee mood and engagement, indicating periods of increased positivity or negativity that may relate to organizational events.
The 30-day rolling window analysis for negative messages flagged users with frequent negative communications, who might benefit from targeted interventions.
Average text lengths and vocabulary sizes provide context on communication style, which could inform customized text processing or sentiment analysis improvements.
# Recommedations
Use techniques like SMOTE, class weighting, or focal loss during model training to improve prediction for underrepresented sentiments (Negative).
Implement automated monitoring of employees flagged by negative message frequency to offer support or investigate underlying issues early.
Use weighted sentiment metrics to identify employees who significantly impact organizational sentiment, both positively and negatively.
Investigate why some users appear in both positive and negative groups — could indicate polarized or nuanced communication styles needing tailored management.
Experiment with n-grams, embedding models, and domain-specific stop words to enhance sentiment model accuracy.
