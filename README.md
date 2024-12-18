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

- **Experimentation**:

  Throughout the Intent Classification task, we conducted extensive experimentation with multiple architectures and preprocessing techniques. Starting with CNN-based models for feature extraction and RNNs (LSTM and GRU) for sequential data modeling, we observed that hybrid architectures combining CNN for feature extraction and GRU for      
 temporal dependencies yielded the best results. We further optimized hyperparameters such as batch size, learning rates, dropout rates, and epochs to balance the model's performance and training efficiency. Class balancing techniques like `class_weight` significantly improved performance on underrepresented classes, and rigorous evaluations on validation and test sets confirmed the robustness of the final model.

- **Evaluation**: Evaluate the model using metrics like **F1-score** and **Confusion Matrix**. Results will show the model's ability to correctly classify intents and identify any biases in predicting certain classes.

### Final Model
- **Model Architecture**:
    - An **Embedding layer** to represent words.
    - A **Conv1D layer** to extract sequential features.
    - Dense layers with `relu` and `softmax` activation for final classification.

- **Training**:
    - Train the model using class balancing techniques.
    - Use metrics like **F1-score** and **Confusion Matrix** to monitor performance.

   **Validation Results**:
    - **Accuracy**: 0.97
    - **F1-score**: 0.82

    ![image](https://github.com/user-attachments/assets/8154fe7d-2a6b-426e-9555-7d37495b153f)

    **Test Results**:
    - **Accuracy**: 0.93
    - **F1-score**: 0.67
      

  <img src="https://github.com/user-attachments/assets/2dd043b2-5209-46fe-afdd-19582d206f58" alt="Confusion Matrix" width="500"/>

### Part 2: Named Entity Recognition (NER)

- **Data Inspection**: Analyze the dataset used for entity recognition tasks. This dataset includes sentences with labeled entities (e.g., cities, dates, business/tourist types). It is important to understand the format of the data and how entities are labeled.

- **Data Preprocessing**:
    - Tokenize the sentences and prepare them for NER tasks by converting text into a sequence of tokens.
    - Label the entities in the sentences using tags such as `B-LOCATION`, `B-DATE`, etc., for the beginning of an entity, and `I-LOCATION`, `I-DATE`, etc., for the continuation of the entity.
  
- **Experimentation**:
  For the Named Entity Recognition (NER) task, we explored multiple deep learning architectures to effectively capture the sequential and contextual dependencies of text. We implemented models based on **Bidirectional GRU**, **LSTM**, and **TimeDistributed Dense layers** to classify tokens into BIO-labeled entities. Experimentation included hyperparameter optimization for embedding dimensions, learning rates, and dropout rates. Additionally, data preprocessing techniques like padding and one-hot encoding for token-level labels were optimized to ensure robust model training. The final Bidirectional GRU model achieved high precision and F1-score, validating its effectiveness in recognizing complex entity patterns within the dataset.
  
- **Evaluation**: Evaluate the NER model using metrics like **Precision** and **F1-score**. The goal is to measure the model's ability to correctly identify entities and minimize false positives/negatives.

### Final Model
- **Model Architecture**:
    - An **Embedding layer** for word representations.
    - A **Bidirectional GRU layer** to capture sequence dependencies in both directions.
    - **TimeDistributed Dense layers** for token-level classification with `softmax`.

- **Training**:
    - Use cross-entropy loss for multi-class classification.
    - Evaluate with **Precision** and **F1-score**.

   **Validation Results**:
    - **Precision**: 0.99
    - **F1-score**: 0.84
      
  ![image](https://github.com/user-attachments/assets/60364964-f24a-4200-a57f-527d9f702d89)

    **Test Results**:
    - **Precision**: 0.99
    - **F1-score**: 0.76

## Contributors

This project was developed by:
- **Marta Juncarol Pi**
- **Jaume Mora Ladària**
- **Abril Risso Matas**
