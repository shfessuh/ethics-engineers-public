# Introduction
This folder contains our initial exploratory analysis of user behavior, comparing those with and without prior history, along with sentiment analysis of news recommendations. Building on this foundation, we implement the LSTUR (Long-Short-Term User Representation) model and the LIGHTFM model for news recommendations using the MIND (Microsoft News Dataset). The LSTUR model, inspired by LIBFM for feature-rich recommendations, leverages both long- and short-term user behaviors, while LIGHTFM utilizes a hybrid collaborative filtering approach to deliver personalized news recommendations.

### cleaning process 
- Behaviors Data: Loaded behaviors.tsv, split History and Impressions into lists, dropped Impression ID, and exploded History into rows (News_ID).
- News Data: Loaded news.tsv with appropriate column names.
- Merged Data: Merged `./MINDsmall_train/behaviors.tsv` and news.tsv on News_ID, then removed duplicate rows based on User ID and News_ID.

## Notebooks/Files

**`Exploratory_Sentiment_analysis.ipynb`**

* Analyzes data for users with and without prior history, exploring metrics such as interaction times and click-through rates (CTR).
* Performs sentiment analysis using `SentimentIntensityAnalyzer()` to examine clicked articles.
* Creates word clouds to visualize words categorized as neutral, positive, or negative in titles and abstracts.


**`MINDsmall_train`**

This file contains a log of user impressions and interactions(`behaviors.tsv`). It also includes the title and abstract embeddings, which were not included in our analysis. 

**`news.tsv`**

This file includes the metadata about news articles (titles, category, abstract, etc.) The predictors used by both models are derived from this file.


**`LSTUR_Model.ipynb`**

* Cleans and merges user behavior and news metadata.
* Implements the LSTUR model with embeddings, GRU, and attention mechanisms.
* Trains the model and evaluates performance using metrics like AUC, MRR, and nDCG@K .
* Model Files: Four .pth files corresponding to the saved checkpoints of the LSUTR model.
    - `lstur_model 1 (Full).pth`
    - `lstur_model 1 (NAN).pth`
    - `lstur_model 1 (Full).pth`
    - `lstur_model 1 (NAN).pth`

**`LIGHTFM_Model.ipynb`**
* Cleans and merges user behavior data and news metadata.
* Optimizes parameters for the model.
* Trains the model and evaluates performance using metrics such as AUC, MRR, and nDCG@K.

**Metrics**
- AUC (Area Under Curve): Measures the model’s ability to rank clicked vs. non-clicked articles.
- MRR (Mean Reciprocal Rank): Assesses the ranking quality of clicked articles.
- nDCG@K (Normalized Discounted Cumulative Gain): Evaluates ranking quality within the top K recommendations.

***Note: For analysis purposes, the TSV files(`news.tsv` & `behaviors.tsv`) are converted into CSV format within each notebook. All notebooks follow the same process of cleaning and merging the behavior and news datasets. The same process is also applied to split data for users with no history.To precisely replicate our results, follow the steps outlined in the notebooks, where all tasks are documented in order for clarity and reproducibility.***

## Dependencies 

**To execute the code, install the following dependencies:**

pip install pandas numpy torch matplotlib scipy torchvision scikit-learn vaderSentiment lightfm tqdm wordcloud nltk

**For GPU support with PyTorch, ensure it is installed using the appropriate version for your system:** 

pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu116

## Contact
For questions or suggestions, please open an issue in the project repository or contact the authors.