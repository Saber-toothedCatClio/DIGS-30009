# DIGS-30009
Project Description

This project builds a supervised machine learning pipeline to classify short segments of Classical Chinese texts into three genre categories: Song–Ming History, Neo-Confucianism (Lixue), and School of Mind (Xinxue). The corpus consists of 20 historical and philosophical works from the Pre-Qin and Song–Ming periods. These texts are split into short character-level chunks, transformed into TF-IDF features, and used to train and compare several classifiers, including Multinomial Naive Bayes, Logistic Regression, Linear Support Vector Machines, RBF-kernel SVM, K-Nearest Neighbors, and Random Forest. The project combines exploratory data analysis of genre signals in Classical Chinese with a critical discussion of challenges such as class imbalance, data leakage between training and test sets, and temporal heterogeneity across periods.

File Overview

Final-Project-Data-Prep-Model-Testing.ipynb

Jupyter notebook that implements the full experimental workflow. It:

Loads and cleans the raw Classical Chinese text files.

Splits texts into genre-labeled chunks using a character-level splitter tailored to Chinese punctuation.

Performs exploratory data analysis, including class distributions, chunk length statistics, and per-document contributions.

Builds TF-IDF features over character uni-, bi-, and trigrams.

Creates stratified train and test splits at the chunk level.

Trains and evaluates multiple classification models and reports accuracy, precision, recall, F1 scores, and confusion matrices.

Ancient_Chinese_Text_Genre_Classification_Final_Report.docx

Final report for the project. It:

Describes the dataset construction process and provides detailed descriptive statistics.

Outlines the theoretical framework for supervised learning, hypothesis spaces, and bias–variance trade-offs.

Documents data cleaning, chunking, feature extraction, and model selection.

Presents quantitative results for all tested models and interprets the confusion patterns in terms of genre and intellectual history.

Offers a critical assessment of limitations (such as chunk-level leakage and temporal mismatch) and proposes concrete directions for future work.

Raw data (for example, under data/raw/)

Original Classical Chinese source texts in plain-text format, organized into subdirectories by genre (for example, SongMing_History, NeoConfucianism, SchoolOfMind). These are the inputs from which the chunk-level dataset is derived.

Processed data (for example, under data/processed/)

CSV files produced by the notebook, such as:

chunks_full.csv: all genre-labeled chunks, with columns for the text, label, source file, and chunk ID.

train.csv: the 80 percent training split used to fit the models.

test.csv: the 20 percent held-out test split used to evaluate generalization performance.
