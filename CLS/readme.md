## Fine-tuning BERT for Text Classification

This notebook demonstrates fine-tuning a BERT (Bidirectional Encoder Representations from Transformers) model for a text classification task. The notebook uses the Hugging Face transformers library and PyTorch for implementation.
A lot of the code used in this notebook is borrowed from this tutorial: https://towardsdatascience.com/fine-tuning-bert-for-text-classification-54e7df642894#5067

The notebook is organized into several sections:

Importing Libraries: This section imports the required libraries for the notebook, including torch, transformers, pandas, numpy, and others.

Loading the Data: In this section, the notebook loads the preprocessed dataset from a CSV file (ProblemData_512.csv). The dataset contains text samples (complaints) and corresponding labels (problems).

Tokenization and Encoding: The text samples are tokenized and encoded using the BERT tokenizer (nlpaueb/bert-base-greek-uncased-v1). The token IDs, attention masks, and labels are extracted and converted into torch tensor format.

Data Splitting: The dataset is split into training and validation sets using the train_test_split function from scikit-learn. The splitting is stratified based on the labels to ensure a balanced distribution in both settings.

Data Loading: The training and validation sets are converted into TensorDataset objects and loaded into DataLoader objects for efficient batch processing during training.

Model Initialization: The Greek BERT model (nlpaueb/bert-base-greek-uncased-v1) is loaded as a BertForSequenceClassification model. The model is configured for sequence classification with five output labels.

Model Training: The model is trained using the training set in a loop that runs for a specified number of epochs. The training loop performs forward and backward passes, updates the model parameters, and tracks the training loss.

Model Evaluation: After each epoch, the model is evaluated on the validation set. Validation loss, accuracy, and F1 score are calculated and displayed.

Early Stopping: The training loop includes early stopping based on the validation loss. If the validation loss does not improve for a certain number of epochs (defined by the patience variable), the training is stopped to prevent overfitting.

Saving the Best Model: During training, the model with the lowest validation loss is saved as best_model.pt.

## Instructions for Use

To use this notebook for fine-tuning a BERT model for text classification:

Prepare your dataset: Replace the path in the data = pd.read_csv(...) line with the way to your dataset file. Ensure that your dataset has a column named "text" for input text samples and a column called "label" for corresponding labels.

Adjust the model and training parameters: Modify the parameters such as MAX_LEN (maximum sequence length), val_ratio (validation set ratio), batch_size, epochs, patience, min_delta, and the learning rate (lr) for the optimizer according to your requirements.

Run the notebook: Execute all the cells in the notebook to tokenize and encode the data, initialize the model, perform training and evaluation, and save the best model.
