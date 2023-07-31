## Fine-tuning BERT for Text Classification

- SHAP (SHapley Additive Explanations) is a game theoretic approach that explains the output results of every machine learning model.
- The Python notebook "our_shap_transformer.ipynb" contains the corresponding functions to explain the category results of our transformers-based classifier.
- The dataset we use is the "Problem_Data_512", which contains all of our complaints categorized with five different labels. Notice that we have removed all objections longer than 512 tokens for computation efficiency (they were not that many).
- We initialize a transformer tokenizer and a Bert classifier using the pre-trained "nlpaueb/bert-base-greek-uncased-v1".
- We use torch.load to load the weights of a model previously computed (BertCLS_10ep.bin) from another notebook.
- The specific notebook runs on GPU, but with only slight changes, it can be executed on CPU.
- We build a function that takes as inputs a list of sentences and outputs the prediction result for every label. This function is used by the shap explainer to describe the importance of every word for our prediction.
- For the explainability part, a basic whitespace tokenizer is first used. Then a transformers.pipeline with a transformers tokenizer is being tried. Then a transformers.TextClassificationPipeline object, and finally, we test the SHAP explainer with a custom-made tokenizer as described in the official tutorials of the library.
