# Intent Classification and Named Entity Recognition in Chatbots

## Description

This project consists of two parts that aim to teach how to process natural language data for chatbot applications. The first part focuses on **Intent Classification**, where the goal is to detect the user's intent from a given sentence. The second part is about **Named Entity Recognition (NER)**, where we identify and classify specific entities within a sentence, such as cities, dates, or specific categories.

These two tasks are fundamental components of building conversational AI systems like chatbots. Intent classification helps in understanding the user's primary goal, while NER extracts relevant entities for more contextualized responses.

## Objectives

- **Part 1: Intent Classification**
  - Learn to classify user intents based on sentence input using deep learning models.
  
- **Part 2: Named Entity Recognition (NER)**
  - Identify and classify entities (like cities, dates, etc.) within sentences using advanced NLP techniques.

## Table of Contents

1. **[Intent Classification (Part 1)](#intent-classification)**
   - [Data Inspection](#section-one)
   - [Data Preprocessing](#section-two)
   - [Model Design and Training](#section-three)
2. **[Named Entity Recognition (NER) (Part 2)](#ner)**
   - [Data Inspection](#section-one)
   - [Data Preprocessing](#section-two)
   - [Model Design and Training](#section-three)
3. **[Final Deliverable](#section-four)**

## Workflow

### Part 1: Intent Classification

- **Load and explore the data**: Analyze the dataset of user queries and their corresponding intent labels. Understand the distribution of different intents and how the data is structured.
  
- **Data Preprocessing**:
    - Tokenize the sentences and prepare them for training by converting them into sequences of word indices using `Tokenizer`.
    - Encode the intent labels using `LabelEncoder` to convert text labels into numerical values.
  
- **Model Design and Training**:
    - Build a deep learning model using **LSTM** or **GRU** layers for sequential data processing.
    - Add dense layers and activation functions to create a classification model.
    - Train the model using the preprocessed data and monitor performance during training using validation data.

- **Evaluation**: Evaluate the model using metrics like **F1-score** and **Confusion Matrix**. Results will show the model's ability to correctly classify intents and identify any biases in predicting certain classes.

    **Example Results**:
    - **Accuracy**: 92%
    - **F1-score**: 0.91 (depending on the dataset and model configuration)
    - Confusion matrix analysis reveals which intents were often misclassified, allowing for targeted improvements.

### Part 2: Named Entity Recognition (NER)

- **Data Inspection**: Analyze the dataset used for entity recognition tasks. This dataset includes sentences with labeled entities (e.g., cities, dates, business/tourist types). It is important to understand the format of the data and how entities are labeled.

- **Data Preprocessing**:
    - Tokenize the sentences and prepare them for NER tasks by converting text into a sequence of tokens.
    - Label the entities in the sentences using tags such as `B-LOCATION`, `B-DATE`, etc., for the beginning of an entity, and `I-LOCATION`, `I-DATE`, etc., for the continuation of the entity.
  
- **Model Design and Training**:
    - Build a sequential model using **LSTM**, **GRU**, or **Bidirectional LSTM** layers to handle sequence labeling.
    - Use **TimeDistributed** layers for classification at the token level.
    - Train the model using the labeled data and fine-tune the parameters.

- **Evaluation**: Evaluate the NER model using metrics like **Precision**, **Recall**, and **F1-score**. The goal is to measure the model's ability to correctly identify entities and minimize false positives/negatives.

    **Example Results**:
    - **Precision**: 0.94
    - **Recall**: 0.89
    - **F1-score**: 0.91 (across all entity categories)
    - The results demonstrate how well the model can extract entities such as locations and dates from user queries.

## Final Deliverable

The final deliverable includes:
- Trained models for both intent classification and named entity recognition.
- A comprehensive evaluation of both models using various metrics.
- Code for data preprocessing, model training, and evaluation, along with visualizations of the results (e.g., confusion matrix for intent classification and entity recognition results).

## Contributors

This project was developed by:
- **Marta Juncarol Pi**
- **Jaume Mora Ladària**
- **Abril Risso Matas**
