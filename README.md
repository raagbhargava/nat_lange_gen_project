# Natural Language Generation and Summarization - Final Project
Final Project for COMS:6998 Natural Language Generation - Zero-Shot Poetry Generation with Plan-And-Generate Framework and Text-Style-Transfer To Emulate Your Favorite Poet
This project is based on the following paper: Yufei Tian and Nanyun Peng. 2022. Zero-shot sonnet generation with discourse-level planning and aesthetics features. arXiv preprint arXiv:2205.01821
I have adapted the code from the their github repository: https://github.com/PlusLabNLP/Sonnet-Gen

To run any code you can simply run the .ipynb files. You might need to adjust the paths.

# Data Set
You can simply download the dataset as a csv file using the links below.

Dataset for Zero-Shot Poetry Generation:
1. Ready Poems from Kaggle: https://www.kaggle.com/datasets/watrgoat/lots-of-poems?select=ready_poems.csv
2. News Summaries from Kaggle: https://www.kaggle.com/datasets/sujalbhagathansda/news-summary
3. ROC short stories from paperwithcode: https://paperswithcode.com/dataset/rocstories
Dataset for Text-Style Transfer
4. Shakespearify from Kaggle: https://www.kaggle.com/datasets/garnavaurha/shakespearify

# Step 0 - Preprocess and data Visulization
I have read in the poetry, new, and roc data and relabelled the column titles to standardize the data frames. I have proprocessed the text to remove stop words, non-alpha symbols, numbers, and lemmatized 
