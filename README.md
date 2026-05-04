# SMS Spam Classification using NLP

## Project Overview

This project demonstrates a machine learning approach to classify SMS messages as either 'spam' or 'ham' (not spam) using Natural Language Processing (NLP) techniques. The goal is to build a robust model that can accurately detect unwanted spam messages.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Key Features](#key-features)
- [Methodology](#methodology)
- [Results](#results)
- [How to Run This Project](#how-to-run-this-project)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Dataset

This project utilizes the **UCI SMS Spam Collection Dataset**, which comprises a collection of legitimate (ham) and spam SMS messages. The dataset is publicly available and commonly used for text classification tasks.

- **Dataset Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/SMS+Spam+Collection)

## Key Features

- **Data Loading and Exploration**: Loading SMS data and initial data inspection.
- **Text Preprocessing**: Cleaning text data (lowercasing, tokenization, removing special characters, stopwords, and stemming) to prepare it for model training.
- **Feature Extraction**: Converting textual data into numerical features using TF-IDF (Term Frequency-Inverse Document Frequency).
- **Machine Learning Model**: Training a Multinomial Naive Bayes classifier.
- **Model Evaluation**: Assessing the model's performance using accuracy metrics.
- **Live Prediction**: Ability to classify new, unseen SMS messages.

## Methodology

1.  **Data Loading**: The SMS dataset is loaded into a pandas DataFrame.
2.  **Data Cleaning**: Irrelevant columns are dropped, and remaining columns are renamed for clarity. Duplicate messages are removed.
3.  **Text Preprocessing**: A custom `clean_text` function is applied to each SMS message, performing:
    *   Lowercasing
    *   Tokenization
    *   Removal of non-alphanumeric characters
    *   Removal of English stopwords
    *   Stemming using Porter Stemmer
4.  **Feature Engineering**: `TfidfVectorizer` is used to transform the cleaned text into a matrix of TF-IDF features. This vectorizer is configured to consider the top 3000 most frequent words.
5.  **Model Training**: The dataset is split into training and testing sets (80% train, 20% test). A `MultinomialNB` classifier from `sklearn` is trained on the TF-IDF features.
6.  **Prediction and Evaluation**: The trained model predicts on the test set, and its accuracy is calculated.

## Results

The trained Multinomial Naive Bayes model achieved an accuracy of approximately **97.10%** on the test set, demonstrating strong performance in distinguishing between spam and ham messages.

## How to Run This Project

To run this project, you will need Python 3 and the necessary libraries. This project is designed to be easily runnable in a Google Colab environment.

### Prerequisites

-   Python 3.x
-   `pandas`
-   `nltk`
-   `scikit-learn`

### Google Colab (Recommended)

1.  **Open the Colab Notebook**: Click on the Colab notebook link provided:
    [https://colab.research.google.com/drive/13woOeg9g7TkyB9af-v3sg38U3SM-u2JU?usp=sharing](https://colab.research.google.com/drive/13woOeg9g7TkyB9af-v3sg38U3SM-u2JU?usp=sharing)
2.  **Save a Copy**: Go to `File > Save a copy in Drive` to create your editable version.
3.  **Mount Google Drive**: In the notebook, you will see a cell to mount Google Drive. This is necessary if your `spam.csv` file is located there. Update the path `'/content/drive/MyDrive/Colab Notebooks/spam.csv'` if your file is stored elsewhere.
4.  **Run All Cells**: Execute all cells sequentially by going to `Runtime > Run all`.

### Local Setup

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/Bijon2002/SMS-Spam-Classification-using-NLP.git
    cd SMS-Spam-Classification-using-NLP
    ```

2.  **Create a Virtual Environment** (optional but recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install Dependencies**:
    ```bash
    pip install pandas nltk scikit-learn
    ```

4.  **Download NLTK Data** (if not already present):
    Open a Python interpreter or add to a script:
    ```python
    import nltk
    nltk.download('stopwords')
    nltk.download('punkt')
    nltk.download('punkt_tab') # This specifically was used in the notebook
    ```

5.  **Place Dataset**: Ensure the `spam.csv` dataset is in the correct directory (e.g., the root of your project or specified path in the notebook).

6.  **Run the Jupyter Notebook**: Open and run the `SMS-Spam-Classification-using-NLP.ipynb` notebook using Jupyter Lab or Jupyter Notebook.
    ```bash
    jupyter notebook
    ```

## Repository Structure

```
SMS-Spam-Classification-using-NLP/
├── SMS-Spam-Classification-using-NLP.ipynb  # The main Jupyter Notebook
├── spam.csv                                # The dataset (should be placed here or accessible via Google Drive)
├── README.md                               # This README file
└── etc.                                    # Other potential files
```

## Contributing

Feel free to fork this repository, open issues, or submit pull requests to improve the project.

## License

This project is open-source and available under the [MIT License](LICENSE.md). 
