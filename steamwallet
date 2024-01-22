import tweepy
import re

# Twitter API credentials
consumer_key = '<get your own>'
consumer_secret = '<get your own>'
access_token = '<get your own>'
access_token_secret = '<get your own>'

# Set up Tweepy
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth, wait_on_rate_limit=True)

# Your regex pattern
pattern = re.compile(r'^[A-Z0-9]{5}-[A-Z0-9]{5}-[A-Z0-9]{5}$')

# Search for tweets
search_query = 'Steam Wallet'
tweets = tweepy.Cursor(api.search_tweets, q=search_query, tweet_mode='extended').items(100)

# Process tweets
for tweet in tweets:
    tweet_text = tweet.full_text
    if pattern.search(tweet_text):
        print(f'Tweet ID: {tweet.id} - {tweet_text}')
