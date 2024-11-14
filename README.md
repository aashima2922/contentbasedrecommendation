# contentbasedrecommendation
Content Based Recommendation system

**Content-Based Recommendation System Using Jaccard Similarity**

This project implements a content-based recommendation system using Jaccard similarity. It recommends items similar to those a user has previously interacted with based on item categories. This approach is useful when recommending items that fall within similar categories to those a user has shown interest in.

How It Works
Data Loading:

The system reads data from three CSV files:
items.csv: Information about each item, including categories.
users.csv: Information about each user, including their country.
events.csv: User interactions with items, with timestamps.
Training - Calculating Item Similarity:

Jaccard similarity is used to find similarity between items based on their categories. Items are encoded with binary values indicating their categories, and Jaccard similarity is calculated to compare items.
Similar items are stored in a similarity matrix, which is later used to generate recommendations.
Session Analysis:

User interactions are grouped into sessions based on an 8-hour gap between events.
Duplicate visits to the same item within a session are removed, and sessions with only one event are excluded.
Statistics like session count, average events per session, and popular categories are calculated.
Generating Recommendations:

For a given session, the system recommends items based on category similarity to those in the session.
It selects the top 5 items most similar to the session history. If no recommendations can be made, popular items are suggested as a fallback.
Evaluation:

The system evaluates recommendations by comparing them with target items for each session, calculating a "hit rate" to measure accuracy.
Usage
Prepare Data Files: Ensure items.csv, users.csv, events.csv, and sessions.csv are in the same directory as the code.

Output:
The program prints session statistics, recommended items, and evaluation results showing recommendation accuracy.
