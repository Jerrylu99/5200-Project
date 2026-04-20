# FedSpeak 2.0 — NLP Pipeline for Central Bank Communications

## Objective
Built an end-to-end natural language processing pipeline to analyze Federal Reserve FOMC meeting minutes, measure policy sentiment, compare text representations, and evaluate their usefulness for predicting monetary tightening regimes.

## Methodology

- Diagnosed and corrected three common NLP pipeline errors:
  - Replaced naive whitespace tokenization with `nltk.word_tokenize()` plus text cleaning and lemmatization
  - Switched from the Harvard GI dictionary to a finance-specific Loughran-McDonald sentiment lexicon
  - Improved TF-IDF feature engineering using tuned `min_df`, `max_df`, and bigram features

- Constructed a reusable Python module (`fomc_sentiment.py`) containing:
  - `preprocess_fomc()` for document cleaning and tokenization
  - `compute_lm_sentiment()` for sentiment and uncertainty scoring
  - `build_tfidf_matrix()` for feature generation

- Generated dense semantic embeddings using the Sentence-Transformers model `all-MiniLM-L6-v2`

- Applied unsupervised learning methods:
  - K-Means clustering on transformer embeddings
  - K-Means clustering on reduced TF-IDF features
  - Compared clustering quality using silhouette scores

- Built an expanding-window time-series evaluation framework to compare predictive power of:
  - TF-IDF features
  - Transformer embeddings

- Estimated logistic regression classifiers and evaluated out-of-sample performance using AUC-ROC across multiple chronological folds

## Key Findings

- Correct domain-specific preprocessing materially improved token quality and reduced false sentiment signals from generic dictionaries.

- Transformer embeddings captured richer semantic structure than bag-of-words methods, particularly for nuanced policy language.

- TF-IDF remained competitive when recurring macroeconomic terminology dominated the signal.

- In predictive testing, **[TF-IDF / Embeddings]** achieved the stronger mean AUC (**[VALUE]**) for identifying tightening policy regimes.

- Results highlight that simple sparse methods can remain effective in structured economic text, while modern embeddings offer advantages when context and tone are important.

## Tools Used

Python, pandas, scikit-learn, NLTK, Sentence-Transformers, Hugging Face Datasets, matplotlib

## Portfolio Relevance

This project demonstrates practical skills in:

- NLP pipeline debugging  
- Financial text analytics  
- Feature engineering  
- Time-series model validation  
- Reusable module development  
- Applied machine learning for macro-financial research
