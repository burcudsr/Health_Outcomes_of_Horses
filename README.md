# 🐎 Horse Health Condition Prediction

This project utilizes deep learning to predict the health outcomes of horses based on clinical data. The model architecture processes both numerical and categorical inputs, employing embedding layers for robust feature representation, and was developed to assist in veterinary diagnostic decision-making. The study was developed as part of the **Kaggle Playground Series - Season 3, Episode 22.**

### 🚀 Live Demo
Explore the prediction model here: **[Horse Health Condition Predictor](https://huggingface.co/spaces/bdaser/Health_Horse)**

### 📊 Dataset Overview
The dataset contains 1,235 training entries and 824 test entries, featuring 29 clinical variables such as `rectal_temp`, `pulse`, `respiratory_rate`, and various surgical indicators.

### 🛠️ Data Preprocessing
The dataset has been meticulously cleaned and preprocessed to ensure model stability:
* **Missing Value Imputation**: Missing values within categorical columns were systematically addressed by assigning a dedicated 'Missing' label, ensuring no data points were discarded.
* **Feature Standardization**: Data consistency was achieved by standardizing specific categorical values into a unified 'Missing' category for optimized model training.
  
### 🧠 Model Architecture
The model is designed with a hybrid architecture:
* **Embeddings**: Categorical inputs are passed through `Embedding` layers to learn dense representations.
* **Concatenation**: Categorical embeddings and numerical inputs are concatenated before being fed into a series of `Dense` layers with `ReLU` activation.
* **Dropout**: `Dropout(0.4)` layers are included to prevent overfitting.
* **Training**: The model utilizes the `Adam` optimizer with a learning rate of 0.0001 and `EarlyStopping` to ensure optimal convergence.

### 🏆 Model Performance
The classification performance on the validation set is summarized below:

| Metric | Lived | Died | Euthanized |
| :--- | :--- | :--- | :--- |
| **Precision** | 0.77 | 0.59 | 0.65 |
| **Recall** | 0.59 | 0.80 | 0.62 |
| **F1-Score** | 0.67 | 0.68 | 0.63 |
