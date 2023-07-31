## SOS complaints classification

- The goal of the notebook "sos_sentences.ipynb" is to point out complaints of high importance, which could, for example, contain injuries or references to legal procedures.
- The dataset we use is the "ComplaintsDataset.csv". We delete empty and duplicate rows.
- We copy the initial complaints column. One will be used for processing, and the other will later be used for visualization. Stopwords are being removed, and apart from the default words, we add some as well.
- We search for references to the aforementioned categories (injuries, legal affairs) for the preprocessing step. We make lists that contain the roots of those references-words. We only keep the complaints we care about and build a new column containing lists of words because we consider the complaint necessary.
- Source: https://towardsdatascience.com/custom-named-entity-recognition-using-spacy-7140ebbb3718. We make the necessary alterations to use the spaCy framework to train a NER model.
- We load the pre-trained 'el_core_news_sm'. 
