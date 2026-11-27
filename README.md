# Spam-Email-Detection-Using-TensorFlow-and-Deep-Learning


## Project Overview

Email is an essential communication tool for individuals and businesses. However, the increasing number of spam emails presents security challenges such as phishing, fraudulent messages, malware distribution, and unwanted advertisements.

This project focuses on developing a Spam Email Detection System using **Deep Learning and Natural Language Processing (NLP)**. The system analyzes email messages and classifies them into two categories: Spam and Ham (Non-Spam).

The model was developed using TensorFlow, Keras, and a Long Short-Term Memory (LSTM) neural network.

The trained model achieved a test accuracy of **94.83%**, demonstrating its ability to identify spam and legitimate email messages.

## Project Objectives

The main objectives of this project were to:

- Analyze an email dataset containing spam and legitimate messages.
- Clean and preprocess textual email data.
- Convert text messages into numerical representations.
- Develop an LSTM-based deep learning model.
- Train and evaluate the model.
- Measure model performance using evaluation metrics.
- Build a system capable of classifying emails as spam or ham.

## Technologies and Libraries

The following tools and libraries were used:

- Python
- TensorFlow
- Keras
- Pandas
- NumPy
- Matplotlib
- Seaborn
- NLTK
- Scikit-learn
- WordCloud

## Dataset Description

The dataset used in this project was:

`spam_ham_dataset.csv`

The dataset contained **5,171 rows and 4 columns**.

| Column | Description |
|---|---|
| Unnamed: 0 | Record identifier |
| label | Spam or Ham category |
| text | Email message |
| label_num | Numerical representation of the label |

<img width="1367" height="495" alt="image" src="https://github.com/user-attachments/assets/c9dbcb9e-3c72-40d3-8ce0-74080f778293" />

The dataset contained more Ham messages than Spam messages, resulting in class imbalance.

To address this, the Ham class was downsampled to create a balanced dataset.

The resulting dataset contained approximately:

- 1,499 Ham messages
- 1,499 Spam messages

## Project Workflow

### 1. Data Exploration

The dataset was examined to understand its structure, dimensions, and class distribution.

The `shape` method was used to determine the number of rows and columns, while a count plot was created to visualize the distribution of Spam and Ham messages.
<img width="1081" height="85" alt="image" src="https://github.com/user-attachments/assets/7e7dd860-e523-471f-8a92-8216b642f13b" />

### 2. Data Balancing

The dataset initially contained significantly more Ham messages than Spam messages.

To reduce class imbalance, the Ham messages were downsampled using Pandas. Both classes were then combined to create a balanced dataset.

### 3. Text Preprocessing

Several Natural Language Processing techniques were applied to prepare the email messages for model training.

These included:

- Removing the word "Subject" from the email text.
- Removing punctuation marks.
- Removing stopwords.
- Cleaning unnecessary text.
- Preparing the messages for numerical conversion.
- <img width="1006" height="721" alt="image" src="https://github.com/user-attachments/assets/a4e19356-d5d9-4584-b020-b211d3b504f1" />


### 4. Text Visualization

WordCloud visualizations were generated separately for Spam and Ham messages.

These visualizations helped identify frequently occurring words and examine differences in vocabulary between the two categories.
<img width="792" height="737" alt="image" src="https://github.com/user-attachments/assets/8b9db314-d9db-46a8-ac8c-b151ee689e97" />


### 5. Tokenization

Tokenization was performed using the Keras Tokenizer.

This process converted words into numerical values that could be processed by the deep learning model.


### 6. Padding

The maximum sequence length was set to 100.

Padding was applied to ensure that all email messages had equal sequence lengths, making them suitable for neural network processing.

### 7. Train-Test Split

The balanced dataset was divided into:

- 80% training data
- 20% testing data

The `train_test_split()` function from Scikit-learn was used.
<img width="971" height="438" alt="image" src="https://github.com/user-attachments/assets/c9255dda-23f2-42e3-afa1-faa811b5a7ba" />


### 8. Label Encoding

The email categories were converted into numerical labels.

| Email Category | Numerical Value |
|---|---|
| Ham | 0 |
| Spam | 1 |

## Deep Learning Model

The model was developed using the TensorFlow Sequential API.

The architecture consisted of the following layers:

### Embedding Layer

The Embedding layer converts numerical word representations into dense vector representations.

It helps the model learn relationships between words and their representations.

### LSTM Layer

The Long Short-Term Memory layer processes sequential text data and learns patterns and contextual relationships within email messages.

### Dense Layer

The Dense layer uses the learned features to support the classification process.

### Output Layer

The output layer uses the Sigmoid activation function to produce a probability indicating whether an email belongs to the Spam category.

## Model Compilation

The model was compiled using:

- **Loss Function:** Binary Crossentropy
- **Optimizer:** Adam
- **Evaluation Metric:** Accuracy

Binary Crossentropy was used because the project involved a binary classification task.

## Model Training

The model was trained using the following parameters:

| Parameter | Value |
|---|---|
| Epochs | 20 |
| Batch Size | 32 |
| Optimizer | Adam |
| Input Sequence Length | 100 |

Two callbacks were implemented to improve the training process:

### EarlyStopping

EarlyStopping monitored validation accuracy and stopped training when improvement was no longer observed for the specified patience period.

### ReduceLROnPlateau

ReduceLROnPlateau monitored validation loss and reduced the learning rate when the model's performance stopped improving.

## Model Evaluation

The trained model was evaluated using the test dataset.

The evaluation produced the following results:

| Evaluation Metric | Result |
|---|---|
| Test Loss | 0.2025 |
| Test Accuracy | 94.83% |
<img width="1160" height="242" alt="image" src="https://github.com/user-attachments/assets/10fca80e-7c6d-4b9a-b0f2-66729a094ab8" />

An accuracy visualization was also created to compare training accuracy and validation accuracy across epochs.

The results showed that training accuracy increased steadily while validation accuracy remained stable.

## Results and Findings

The model successfully learned patterns that distinguish Spam emails from legitimate messages.

The project demonstrated that:

- Text preprocessing helped prepare the email messages for classification.
- Tokenization converted textual information into numerical sequences.
- Padding enabled consistent input dimensions.
- The LSTM layer learned patterns from sequential email text.
- Dataset balancing addressed the difference in class distribution.
- The model achieved a test accuracy of approximately 94.83%.
- <img width="842" height="537" alt="image" src="https://github.com/user-attachments/assets/4766dc4f-fc99-493b-a7a2-1cc316fa97e9" />


## Conclusion

This project demonstrated the application of Deep Learning and Natural Language Processing to email spam classification.

By combining text preprocessing, dataset balancing, tokenization, padding, and an LSTM neural network, the system achieved a test accuracy of 94.83%.

The results show that deep learning can be used to identify patterns in email messages and distinguish spam from legitimate communication.

## Future Improvements

Possible improvements to the project include:

- Using larger and more recent email datasets.
- Implementing a Bidirectional LSTM model.
- Exploring Transformer-based architectures such as BERT.
- Performing hyperparameter optimization.
- Developing a web-based application.
- Integrating the model with real-world email platforms.
