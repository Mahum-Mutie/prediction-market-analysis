# prediction-market-analysis

## Question
what types of questions attract the most trading activity and engagement?

At the beginning of the project, I originally wanted to explore “market conviction”. My original question was “What types of questions attract the most market conviction?” but after inspecting the dataset, I realized that liquidity values were unavailable/unusable. Because of that, I pivoted the question to focus on trading activity and engagement using trading volume which is “what types of questions attract the most trading activity and engagement?"
 
## Approach
I used a subset from Jon Becker’s Prediction Market Analysis repository:
polymarket → markets → markets_10000_20000.parquet
I worked with a subset instead of the full 36GB dataset to keep the analysis focused, manageable, and relevant to the onboarding task. 

##  Attempt 1: Initial Analysis 
In the first notebook (prediction_market_analysis_PT1.ipynb), I explored the dataset, tested different possible questions, and built an initial keyword based classification system.
The first version helped me understand what columns were useful, which fields were unavailable, how prediction market questions were structured, and how categories could be created from text data. 

However, after I completed the first version, it still had many limitations that I wanted to improve such as the “Other” category being too large, some categories being too broad, the dataset needing more structured cleaning and the keyword classification needing refinement. Considering that I still had loads of time ahead of me, I decided to go back and redo my analysis to improve my previous limitations. 

## Attempt 2: Final Refined Analysis
In the second notebook (FINAL_prediction_market_analysis.ipynb), I restarted the process with a cleaner pipeline. I started off by checking the dataset structure using ‘.info()’ and ‘.describe()’. Then, I cleaned the dataset by checked missing values, removing rows missing key fields like ‘question’ or ‘volume’, removed duplicate questions, converted ‘volume’ into numeric format. Then I continued cleaning the questions by lowercasing, removing punctuation, and removing extra spaces. After cleaning the dataset like attempt 1, I removed stopwords to improve keyword quality. Then I used keyword frequency analysis to identify common themes and refined categories based on actual words appearing in the dataset. 

The final analysis used a keyword based classification system to sort prediction market questions into categories Politics, Sports, Economics, Crypto, Tech, Legal, Entertainment, Weather and Other. The main assumption was that trading volume can be used as a proxy for market engagement. Since liquidity was unavailable, volume was the strongest usable signal for understanding which topics attracted the most activity. Keyword based classification is not perfect, but it was useful for creating an interpretable baseline model.

## Attempt 1: Findings
- there were 8 main categories within this dataset which included sports, politics, economics, tech, crypto, legal, entertainment, and other.
- Sports questions have the highest trading activity by a large margin
- Politics is the second strongest category
- Economics, tech, and crypto fall into a mid tier
- Legal and entertainment questions have lower engagement
- Even after refinement, some questions remain in "Other" due to real-world complexity

## Attempt 2: Findings 
- There were 9 main categories within this dataset which included Politics, Sports, Tech, Events, Crypto, Economics, Legal, Entertainment, and Other.
- Politics and sports made up the largest share of prediction market questions
- Sports related questions generated very high trading activity
- Tech, crypto, economics, legal, entertainment, and weather appeared less frequently
- The “Other” category became much smaller after improving the cleaning and classification process
- Before cleaning and classification, “other” category was the third largest. After classification it was placed at number 6.
- When cleaning and classifying, majority of the questions were about were a mix of politics and sports
- A key takeaway is that prediction markets appear to attract the most engagement around high-attention, time-sensitive topics such as sports and politics.

## Attempt 1: Visualization
Average Trading Volume by Category
<img width="989" height="590" alt="download" src="https://github.com/user-attachments/assets/74299d05-5e48-4106-9295-a1c369b364eb" />

Distribution of Questions by Category
<img width="794" height="658" alt="download" src="https://github.com/user-attachments/assets/2578c5b3-b5a9-40e0-bf7c-9f1e4a81f438" />

## Attempt 2: Visualization 
Average Trading Volume by Category
<img width="1187" height="690" alt="download" src="https://github.com/user-attachments/assets/8d04b595-25d6-462d-bcab-c3fa510d5544" />

Distribution of Prediction Market Categories
<img width="1089" height="891" alt="download" src="https://github.com/user-attachments/assets/ad1e4673-2729-4548-806e-e1560d570bc2" />

## Next Steps 
If I had another week to do this project again, or another week to continue I would:
- analyze trade level data for deeper user behavior insights
- compare results across multiple dataset chunks
- build an interactive dashboard to filter by category, volume, and date 


