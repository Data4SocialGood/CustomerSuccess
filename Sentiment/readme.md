## Sentiment analysis

In this notebook is implemented a method to calculate sentiment on complaints that are given through a ".csv" file, using a Greek feeling dictionary named Fixed_Greek_Lexicon.csv.

The notebook is separated into the following sections:

    Importing Libraries: This section imports the required libraries for the notebook to process text in Greek and visualize the results, including langdetect, simplemma, greek_stemmer, nltk, and others.

    Loading the Data: In this section, the notebook loads the preprocessed dataset from a CSV file. The dataset contains text samples (complaints) and their label.

Loading Libraries: Now the notebook loads a dictionary that contains a great number of Greek words and for each of them they provide a range of feeling.

    Text Processing: Through the function stem_lem the text samples were turned into a uniform format by removing the punctuation, and stopwords, and turning all letters into lowercase.

    Feelings Calculator: 
After the text is lemmatized the dataset is represented as a "bag" (or unordered set) of its constituent words, disregarding grammar, word order, and context. 
Then based on the dictionary the "feeling_range"  function calculate the range of a feeling by calculating the mean value of the feeling range of the words that it contains.

Instructions for Use

To use this notebook:

    Prepare your dataset: Replace the path in the oasa_dataset = pd.read_csv('.. .csv')
 line with the path to your dataset file. Ensure that your dataset has a column named "text" for input text samples and a column named "label" for corresponding labels. 
Also, be sure you add a feeling dictionary in Greek and replace the path dataset = pd.read_csv('... .csv'). Again ensure that your dataset has a column named term, Sadness3, etc.
 Otherwise, adjust the input when creating label_list_.... and label_array_...

    Run the notebook: Execute all the cells in the notebook.
