# Google Play Store Sentiment Analysis: DANA Application

This repository contains an end-to-end Natural Language Processing (NLP) project focused on analyzing user sentiments from the DANA mobile application reviews using Deep Learning architectures.

## Educational Context
This project was developed as a final submission for **Dicoding Academy**, conducted as part of the program in collaboration with **Pijak** and **IBM SkillsBuild**. The core objective of this assignment is to demonstrate practical competence in:
- Independent data sourcing via web scraping.
- Implementing robust Natural Language Processing (NLP) preprocessing pipelines.
- Designing, training, and optimizing Sequential Deep Learning models (LSTM/GRU) using TensorFlow/Keras.
- Demonstrating the impact of data quality and experimental workflows on machine learning performance.

## Project Overview
This project explores how data-label quality affects model performance. The workflow consists of iterating through 3 different experimental training schemes across LSTM and GRU architectures to find the most optimal deployment strategy, eventually achieving a high-accuracy model that meets the certification criteria.

## Pipeline Breakdown
1. **Data Scraping**: Extracted 12,500+ raw reviews from the Google Play Store utilizing the `google-play-scraper` library to ensure a substantial dataset.
2. **Text Preprocessing**: Cleaned text data by handling case folding, stripping special characters, digits, emojis, and normalizing whitespace.
3. **Lexicon-Based Relabeling**: Replaced initial rating-based labels with a textual Lexicon approach to minimize noisy labels (e.g., users giving 5 stars but writing negative complaints).
4. **Tokenization & Padding**: Converted cleaned text into numerical sequences with a predefined sequence length of 100 tokens.
5. **Model Architecture & Experiments**:
   - **Scheme 1**: LSTM model trained on raw star-rating labels (Validation Accuracy: ~66%).
   - **Scheme 2**: GRU model trained on raw star-rating labels (Validation Accuracy: ~64%).
   - **Scheme 3**: GRU model trained on Lexicon-cleaned labels (Validation Accuracy: **96.34%**).

## Final Results
By resolving label contradictions and shifting to a content-driven labeling strategy, the optimized GRU model effectively captured sentiment semantics, boosting accuracy to **96.34%** on the validation set without overfitting.

## Repository Structure
- `scraping.ipynb`: Notebook containing the data extraction logic.
- `submission.ipynb`: Main notebook handling data preprocessing, model experiments, and inference testing.
- `dataset_playstore_dana.csv`: The raw scraped dataset.
- `requirements.txt`: List of dependencies required to run the notebooks.
