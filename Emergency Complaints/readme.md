## SOS complaints classification

- The goals of the notebook "sos_sentences.ipynb" is to point out complaints of high importance which could for example contain injuries or references to legal procedures.
- The dataset we use is the "ComplaintsDataset.csv". We delete empty and duplicate rows.
- We copy the initial complaints column. One will be used for processing and the other one will later be used for visualizations. Stopwords are being removed and apart from the default words, we add some as well.
- For the preprocessing step, we search for references to the aforementioned categories (injuries, legal affairs). We make lists that contain the roots of those references-words. We only keep the complaints we care about and we build a new column containing lists of words because of which we consider the complaint important.
- Source: https://towardsdatascience.com/custom-named-entity-recognition-using-spacy-7140ebbb3718. We make the alterations needed so that we can use the spaCy framework to train a NER model.
- We load the pre-trained 'el_core_news_sm'. 
