IMDB Movie Review Sentiment Analysis
This project implements an end-to-end deep learning solution for sentiment analysis on IMDB movie reviews, using embedding layers and a Simple RNN to classify reviews as positive or negative. It features text preprocessing with word indexing, padded sequences, and provides a real-time prediction app using Streamlit.



Overview
Built a deep learning model with Embedding and SimpleRNN layers to classify IMDB movie reviews as positive or negative.

Text preprocessing includes word index encoding and padded sequences for consistent input length.

Developed a real-time web app using Streamlit for interactive sentiment prediction.

Demo
To try the app locally:

Run the Streamlit server

Enter a movie review to classify it

Features
Deep learning sentiment classifier based on IMDB dataset

Efficient text preprocessing (tokenization, encoding, padding)

Interactive web interface via Streamlit

Easily extensible for improved models or datasets

Project Structure
text
/
├── embedding.ipynb       # Embedding techniques demonstration[2]
├── simplernn.ipynb       # Complete training pipeline with SimpleRNN[6]
├── prediction.ipynb      # Notebook for making and analyzing predictions[4]
├── main.py               # Streamlit app for real-time user input[3]
├── simple_rnn_imdb.h5    # Trained model weights (should be generated after training)
├── requirements.txt      # Python dependencies[5]
Installation
Clone the repository.

Install the required packages:

bash
pip install -r requirements.txt
How to Run
1. Train the Model (if model file not available)

Run the complete notebook (simplernn.ipynb) to preprocess data, train, and save the model as simple_rnn_imdb.h5.

2. Launch the App

bash
streamlit run main.py
Enter any movie review text in the text area and click 'Classify' to get the sentiment and prediction score.

Model Architecture
Embedding Layer: Transforms word indices into dense vectors.

SimpleRNN Layer: Captures temporal dependencies in text.

Dense Output Layer: Outputs sentiment probability using sigmoid activation.

Example summary (see simplernn.ipynb/prediction.ipynb):

text
Model: "sequential_1"
_________________________________________________________________
 Layer (type)         Output Shape      Param #
=================================================================
 embedding (Embedding)  (None, 500, 128)   1280000
 simple_rnn (SimpleRNN)(None, 128)        32896
 dense (Dense)           (None, 1)              129
=================================================================
Total params: 1,313,025
Trainable params: 1,313,025
Example Usage
Predict in Python

See prediction.ipynb for programmatic inference:

python
review = "This movie was fantastic! The acting was great and the plot was thrilling."
sentiment, score = predict_sentiment(review)
print(sentiment, score)
Via Streamlit App

Input review, click 'Classify', and view sentiment with score in the web UI.

Acknowledgements
IMDB dataset from Keras/TensorFlow Datasets

Streamlit for the interactive web interface
