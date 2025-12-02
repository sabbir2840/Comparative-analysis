1. Introduction
This project investigates whether topic modeling can enhance text classification performance. Using the Rotten Tomatoes dataset, we apply a traditional machine learning pipeline to compare classification accuracy before and after integrating topic-based features.

2. Dataset Overview
The dataset contains movie-related metadata and critic review text. For this experiment, we used a cleaned text column as input along with its categorical label. Preprocessing included lowercasing, punctuation removal, stop word filtering, and lemmatization.

3. Baseline Model (Before Topic Modeling)
The baseline classifier uses:
  1.	TF-IDF vectorization
  2.	Logistic Regression

4. Topic Modeling
4.1 Token-Augmented Modeling
The assigned topic label (e.g., “topic3”) was appended to each document before vectorization.
This provides a lightweight way to inject semantic topic information into the text.

4.2 Topic Vector Fusion
Each document's topic probability distribution (e.g., [0.12, 0.45, 0.08, ...]) was concatenated with the TF-IDF vectors, forming a hybrid feature representation.
This method captures richer semantic structure.

<img width="1289" height="211" alt="image" src="https://github.com/user-attachments/assets/1502639f-3879-4247-8c81-2de78eaf77ec" />
Fig: Metrics chart

5. Classification After Topic Modeling
Both post-topic approaches used Logistic Regression on augmented feature sets.
Results generally showed:
Improvement after Step 15, indicating that simple topic tokens add informative context.
Further improvement after Step 16, due to the integration of dense semantic topic vectors
The hybrid model leverages both lexical and thematic information, producing a more discriminative representation.

<img width="1379" height="484" alt="image" src="https://github.com/user-attachments/assets/fdde0ea7-994c-4448-b4c6-a5727e1ee798" />
Fig: Before and after modeling

6. Conclusion
The experiment demonstrates that incorporating topic modeling—whether by adding topic labels or using full topic probability vectors—can enhance text classification performance.
While the baseline TF-IDF model performs reasonably well, topic-aware models provide better semantic understanding, improved class separability and higher overall accuracy
Thus, topic modeling is an effective feature-enrichment technique for traditional machine learning classifiers.
