# Hierarchical_Emotion_Classifier_Japanese
The Python notebook (Final_combiningmodelstohierarch.ipynb) demonstrates the development of a hierarchical emotion classifier using Bert models, particularly focusing on analyzing Japanese text.

Library Installation and Data Acquisition:
Essential libraries such as fugashi, ipadic, transformers, and datasets are installed for Japanese text processing and machine learning.
The dataset (wrime-ver2.tsv) is downloaded from a GitHub repository. This dataset, known as WRIME, contains sentences labeled with various emotional intensities and sentiments.

Data Preprocessing:
The data is loaded into a pandas DataFrame, and preprocessing steps are applied to compute the maximum emotion intensity for each row. This involves determining the primary emotion by comparing intensities and handling ties in emotion intensities through sentiment closeness to readers' average sentiments.
Emotion and Sentiment Classification:

Multiple pretrained models are loaded for classifying text into different emotion categories and intensities, such as neutral vs. emotional, positive vs. negative, and specific emotions like joy, trust, anger, and disgust.
The models used are specific to the Japanese language and are fine-tuned for differentiating among various emotional contexts. These include binary classifiers for initial broad categorization and more refined classifiers for specific emotions.

Model Application and Evaluation:
Functions are defined for each classification step, reflecting a hierarchical decision process where text is first categorized into broad classes (neutral or emotional), followed by finer categorization within the emotional texts (positive, negative, surprise, etc.).
The test set is processed through these classifiers, and predictions are made for each sentence. Performance metrics such as accuracy, precision, recall, and F1-score are calculated to evaluate the models.

Error Analysis:
The model’s predictions are compared against the actual labels to identify incorrect predictions. These instances are exported to a CSV file for further analysis, potentially guiding improvements in model performance or data preprocessing.

Threshold Optimization:
A grid search is conducted over various threshold values used in the classifiers to find the optimal settings that maximize the F1-score. This step aims to fine-tune the decision boundaries for the classification tasks, enhancing the overall accuracy and reliability of the model.
Hierarchical Classification Strategy:

The classification strategy is hierarchical, starting with broad distinctions (neutral vs. emotional) and drilling down into more specific emotional states. This approach helps in managing the complexity of human emotions in text, leveraging the strengths of different specialized models at each hierarchy level.
