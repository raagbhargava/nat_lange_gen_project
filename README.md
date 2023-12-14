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
preprocess_and_data_exploration.ipynb - This code reads in the poetry, new, and roc data and relabelled the column titles to standardize the data frames. It preprocessed the text to remove stop words, non-alpha symbols, and numbers. It lemmatizes words and lowers all the words. It calculates the diversity score for each data set and visualized it. It calculates the cosine similarity for title and text pairs for each data set and visualizes it.

dependencies: none
path: you will need to download the csv files from the links above
commands: none; just run the ipynb file

# Step 1 - Keyword Extraction and Generation
keybert_keyword_extraction.ipynb - This code reads in the csv files, preprocess the data, uses keybert algorithm to extract keywords from the text, and outputs title and keywords into a .json file. 
yake_keyword_extraction.ipynb - This code reads in the csv files, preprocess the data, uses yake algorithm to extract keywords from the text, and outputs title and keywords into a .json file. 
data - contains the .json files for all 3 datasets extracted using both the algorithms. 
bart-large-keywords.ipynb - It trains a bart-large model on title-keywords pair.
inference_bart_keywords.ipynb - Generates keywords given a title

dependencies: 
pip install yake
pip install keybert
pip install keybert[flair]
pip install keybert[gensim]
pip install keybert[spacy]
pip install keybert[use]
pip install --upgrade urllib3
pip install torch
pip install spacy
pip install sentencepiece
pip install transformers

path: you will need to adjust the paths to the .json files and 
commands: none; just run the ipynb files

# Step 2 - Rhyme Generation
generate_rhyme.ipynb - Generates candidate rhyme words for the third keyword using the pronouncing library. Selects only keywords that are sensible english words using the nltk corpus. Then selects the first word from the list and replaces the third keyword from the alternating sentence so they rhyme. 

dependencies: 
pip install pronouncing

path: none
commands: none; just run the ipynb files

# Step 3 - Metaphor Incorporation
pick_random_word.ipynb - Randomly picks a keyword, except the rhyming words, to generate a metaphor.
I use the following interactive system to generate a metaphor: http://language-play.com/metaphoria/

dependencies: none
path: none
commands: none; just run the ipynb files

# Step 4 - Poetry Generation
poetry_generation.ipynb - Uses GPT-Neo-2.7B finetuned on Tian and Peng, 2022 dataset to generate coherent poetry in reverse to enforce rhyme words. Meter-and-rhyme, keywords, and metaphors were also enforced. 

dependencies: none
path: none
commands: none; just run the ipynb files

# Step 5 - Automatic Evaluation
eval,ipynb - Calculates the lexical diversity score (unique words / total words) for a given poem
human evluation.doc - Contains human evluation data

dependencies: none
path: none
commands: none; just run the ipynb files

# Step 6 - Text Style Transfer
bart-large-style transfer.ipynb - Trains a bart large model on pair shakespearean text and its english translation.
inference_shakespeare.ipynb - Uses the trained bart-large to perform text style transfer to get a poem to sound like shakespeare

dependencies: none
path: none
commands: none; just run the ipynb files