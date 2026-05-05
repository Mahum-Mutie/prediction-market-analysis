# prediction-market-analysis

## Question
Analyzing which types of prediction market questions attract the most trading activity 

Throughout the process, my question ended up changing twice. Initially, my question was "what types of questions attract the most market conviction?". With this question, we needed to know both liquidity and volume to measure market conviction however, liquidity data was unavailable. Which is why I decided to finalize the question "what types of questions attract the most trading activity and engagement?". 

## Approach
- I started off by choosing my data set off of John Beckers Prediction Market Analysis Repo. (polymarket --> markets --> markets_0_10000.parquet) 
- I uploaded my data set onto Google Colab, then loaded and explored the prediction market dataset
- I had some trial and error in terms of questions. my frist question didnt have valid data available so I explored the data to ask a question where the answer could be predictable and accurate.
- when I chose an appropiate question that had all the data required, I Built a keyword based classification system to categorize questions into the different sections including Sports, Politics, Economics, Crypto, Tech, Legal, Entertainment, Other.
- I iteratively refined categories by analyzing keyword frequency to reduce the size of "Other" multiple times until "other" consitied of key words like  “the” “it” “and”.

## Findings
- there were 8 main categories within this dataset which included sports, politics, economics, tech, crypto, legal, entertainment, and other.
- Sports questions have the highest trading activity by a large margin
- Politics is the second strongest category
- Economics, tech, and crypto fall into a mid-tier
- Legal and entertainment questions have lower engagement
- Even after refinement, some questions remain in "Other" due to real-world complexity

## Visualization
Average Trading Volume by Category
<img width="989" height="590" alt="download" src="https://github.com/user-attachments/assets/74299d05-5e48-4106-9295-a1c369b364eb" />

Distribution of Questions by Category
<img width="794" height="658" alt="download" src="https://github.com/user-attachments/assets/2578c5b3-b5a9-40e0-bf7c-9f1e4a81f438" />


## Next Steps 
- If I had another week to do this project again, or another week to continue I would
    - focus on making the category "other" much smaller so the categoroes could be more accurate
    - clean the data set more thorougly so we could remove duplicates, handle missing values, and normalize numeric fields

