## Introduction
This project implements the LSTUR (Long-Short-Term User Representation) model for news recommendation using the MIND (Microsoft News Dataset). The goal is to understand user engagement patterns, address the “cold-start” problem, and analyze how diversity and sentiment in news recommendations influence user interactions.

## Project Structure
1. Code Overview
The notebook includes the following key sections:
* Data Preprocessing: Cleaning and merging the behaviors and news datasets into a usable format.
* Dataset Preparation: Creating PyTorch datasets and loaders for model training and testing.
* Model Definition: LSTUR model architecture using embedding layers, GRU, and attention mechanism.
* Training and Evaluation: Training the model and calculating performance metrics such as AUC, MRR, and nDCG@K.

2. Dependencies
Install the following dependencies to execute the code:
pip install torch torchvision scikit-learn pandas numpy matplotlib tqdm wordcloud nltk

Ensure PyTorch is installed with GPU support if available:
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu116

3. Dataset
Source: MIND Dataset.
Structure:
* behaviors.tsv: Logs of user impressions and interactions.
* news.tsv: Metadata about news articles (title, category, abstract, etc.).

Note: Due to privacy concerns, the raw dataset is not included. You can download it from the link above.

Preprocessing Steps:
1. Split History and Impressions into lists.
2. Convert Time to datetime format.
3. Merge behaviors and news data on News ID.

4. How to Repeat Results
Follow these steps to reproduce the results:

1. Download and Extract the MIND Dataset:
* Place the dataset in a directory (e.g., MINDsmall_train/).
2. Run Data Preprocessing:
* Clean and merge the behaviors and news datasets using the code in the notebook.
3. Train the Model:
* Use the LSTUR implementation in the notebook. Adjust hyperparameters if needed.
4. Evaluate the Model:
* Metrics such as AUC, MRR, and nDCG@K can be calculated using the provided functions.

5. Performance Metrics
The model is evaluated using:

* AUC (Area Under Curve): Measures the model’s ability to rank clicked vs. non-clicked articles.
* MRR (Mean Reciprocal Rank): Assesses the ranking quality of clicked articles.
* nDCG@K (Normalized Discounted Cumulative Gain): Evaluates ranking quality within the top K recommendations.

6. Model Variations

1. Full Dataset:
* Trained on all available user interactions.
* Performance Metrics:
* AUC: 0.5965
* MRR: 0.2068
* nDCG@5: 0.1443
* nDCG@10: 0.1967

2. Cold-Start Analysis:
* Focuses on users with minimal interaction history.
* Analyzes diversity and sentiment in recommendations.

7. Contact
For questions or suggestions, please open an issue in the project repository or contact the author.