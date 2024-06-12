# Hierarchical Emotion Classifier for Japanese Text

This repository contains the `Final_combiningmodelstohierarch.ipynb`, a Python notebook that demonstrates the development of a hierarchical emotion classifier using Bert models. 

## Library Installation and Data Acquisition

```bash
!pip install fugashi ipadic transformers datasets
```

- **Libraries**: The essential libraries for Japanese text processing and machine learning are `fugashi`, `ipadic`, `transformers`, and `datasets`.
- **Data**: The dataset used is `wrime-ver2.tsv`, sourced from a GitHub repository. Known as WRIME, it features sentences labeled with various emotional intensities and sentiments.

## Data Preprocessing

- Data is loaded into a pandas DataFrame.
- **Computation**: Calculate the maximum emotion intensity for each row.
- **Primary Emotion Determination**: Identify the primary emotion by comparing intensities and resolving ties based on closeness to readers' average sentiments.

## Emotion and Sentiment Classification

- **Models**: Utilize multiple pretrained Bert models fine-tuned for differentiating among various emotional contexts.
- **Categories**: Classify text into broad classes such as neutral vs. emotional, positive vs. negative, and specific emotions like joy, trust, anger, and disgust.

## Model Application and Evaluation

- **Hierarchical Classification**: Implement a hierarchical decision process where text is first categorized into broad classes followed by finer categorization.
- **Metrics**: Evaluate the models based on accuracy, precision, recall, and F1-score, using predictions made on the test set.

## Error Analysis

- **Comparison**: Match the model’s predictions against actual labels to pinpoint inaccuracies.
- **Output**: Export instances of incorrect predictions to a CSV file for further examination.

## Threshold Optimization

- Conduct a grid search over various threshold values to optimize decision boundaries, aiming to enhance the F1-score and overall model performance.

## Hierarchical Classification Strategy

- The classifier operates hierarchically, starting from broad distinctions (neutral vs. emotional) and drilling down into finer emotional states. This method effectively handles the complexity of human emotions in textual data.
