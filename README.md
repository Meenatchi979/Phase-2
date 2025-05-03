import nltk
from nltk.sentiment import SentimentIntensityAnalyzer

# Download the VADER lexicon
nltk.download('vader_lexicon')

# Initialize Sentiment Analyzer
sia = SentimentIntensityAnalyzer()

# Sample Social Media Comments
comments = [
    "I love this new product! It's amazing! 😍",
    "This is the worst update ever. Totally disappointed! 😡",
    "Not bad, could be improved though.",
    "Wow! Incredible job on this project. Well done!",
    "I feel so sad today. Nothing is going right. 😢"
]

# Analyzing Sentiments
for comment in comments:
    sentiment_score = sia.polarity_scores(comment)
    compound_score = sentiment_score['compound']
    
    # Classify sentiment
    if compound_score >= 0.05:
        sentiment = "Positive"
    elif compound_score <= -0.05:
        sentiment = "Negative"
    else:
        sentiment = "Neutral"
    
    print(f"Text: {comment}")
    print(f"Sentiment: {sentiment}")
    print("-" * 40)

    OUTPUT:
    Text: I love this new product! It's amazing! 😍
Sentiment: Positive
----------------------------------------
Text: This is the worst update ever. Totally disappointed! 😡
Sentiment: Negative
----------------------------------------
Text: Not bad, could be improved though.
Sentiment: Neutral
----------------------------------------
Text: Wow! Incredible job on this project. Well done!
Sentiment: Positive
----------------------------------------
Text: I feel so sad today. Nothing is going right. 😢
Sentiment: Negative
----------------------------------------
