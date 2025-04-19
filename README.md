# BackTesting Framework Using Machine Learning Models
This is a backtesting framework that utilises Market data, sentiment and whale address to predict the signal using machine learning models 

## Submission
Slide link: https://www.canva.com/design/DAGk_kM3oik/3BBEV4MQxRzXJJXmZ6FsLA/edit?utm_content=DAGk_kM3oik&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
## Machine Learning Models Used

1. **FinBERT**
   - Identifies the sentiment of news articles and Reddit posts.
2. **HMM-GMM**
   - Detects hidden market regimes and their intensities.
3. **Reinforcement Learning**
   - Predicts trading signals based on market regimes and other factors.
   - Uses a combination of step return, Sharpe Ratio, maximum drawdown, and trade frequency as rewards.
4. **XGBoost**
   - Predicts trading signals based on engineered sentiment and behavioral features.


## Requirements

Install all required packages with:

```bash
pip install -r requirements.txt
```

# Structure
1. **Import Libraries**
2. **Fetch data from API**
   - Define API URLs
   - Fetch market data
   - Combine all fetched data into a csv file
3. **Data Preprocessing**
   - Check missing values
   - Update the dataset
4. **Sentiment Data**
   - Extract submissions, upvotes, comments and all relevant information from reddit (filter with subreddit)
   - Extract news from CoinDesk
   - FinBERT model to get the sentiment scores
   - Use Buzz Factor to calculate the influence of the news and reddit submissions
5. **BackTest**
   - A backtester that can return the sharpe ratio, maximum drawdown, trade frequency and result of backtest
6. **HMM-GMM Model**
   - Include features to fine tune and find the best parameter
   - Map the hidden regime to signal
   - Use backtester class to evaluate the performance of each of the combinations of features
7. **Reinforcement Learning**
   - Use combination of step return, sharpe ratio, maximum markdown, and trade frequency as rewards
   - Train the agent repeatedly with the train dataset
8. **Predict Signal with Sentiment Data Using XGBoost**
   - Include the buzz factor, whale scoring, and market regimes into a single engineered score
   - The strategy is evaluated using Sharpe Ratio, Cumulative Return and Max Markdown
     
# How To Run
1. Clone this repo:
```bash
git clone https://github.com/ngernyi/UMHACK-2025-KITA-KOD.git
```

2. Install all required packages with:

```bash
pip install -r requirements.txt
```

3. Run the main file:

Open and execute `KITA_KOD_UMH2025_FullCode.ipynb` in Jupyter Notebook.

# Expected output
1. A Csv file consists of a list of signal with the result of backtesting
   
![image](https://github.com/user-attachments/assets/8e88ecd0-d6e6-4a16-9f21-d9418328f222)

2. Sharpe Ratio, Maximum Markdown and Trade Frequency
   
![WhatsApp Image 2025-04-20 at 07 53 55_4a3b9dde](https://github.com/user-attachments/assets/36ec915b-6985-4cea-b38b-79da65020696)

3. Equity Vs Price Graph
   
![WhatsApp Image 2025-04-20 at 07 54 15_d2e08411](https://github.com/user-attachments/assets/d9f291e8-8fb6-4f22-819d-5fa8f9c0cc30)

4. Drawdown over time

![WhatsApp Image 2025-04-20 at 07 55 25_c888022e](https://github.com/user-attachments/assets/a887bfb3-f8c1-4bee-956c-606a9757a4cc)

