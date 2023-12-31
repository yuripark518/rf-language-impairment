# The Prediction Problem

## Research Question Formulation:
* **Objective**: The traditional approach to diagnosing Autism Spectrum Disorder (ASD) has encountered significant challenges, including inconvenience and potential inaccuracy. Typically, this method necessitated the presence of clinicians and trained linguists. Diagnoses were often established by comparing scores to the averages of a reference population. Children scoring at least 1.25 times below the standard deviation (SD) in two or more measures were considered to have Language Impairment (LI). However, Campbell et al. (1997) noted that such norm-referenced tests could be biased, leading to inaccuracies (Lee, 2016, pg. 4). Furthermore, with overlapping features, the difficulty of correctly identifying differences between Specific Language Impairment (SLI) and ASD, and even other disabilities, was found to be challenging through the specialist's record alone. Thus, the objective measurements provided by machine learning serve to potentially address the initial problem of misdiagnosis from a human standpoint.

* **Significance**: To address the challenges of inaccessibility and inaccuracy, Lee's research proposes leveraging Natural Language Processing (NLP) and Machine Learning (ML). This approach involves employing NLP to extract linguistic features indicative of Autism Spectrum Disorder (ASD) and Specific Language Impairment (SLI). Subsequently, Machine Learning algorithms are utilized to predict the likelihood of a child having Language Impairment (LI), encompassing ASD or SLI, based solely on text analysis (Lee, 2016, pg. 1). Specifically, the classification process aims to achieve an acceptable accuracy rating for predicting labels in the dataset (Lee, 2016, pg. 8). This technological advancement seeks to enhance the accessibility and accuracy of the ASD diagnostic process (Lee, 2016, pg. 4). However, given that Lee's research was conducted in 2016, recent advancements in the field have led to further investigations. To ensure the continued relevance and potential impact of Lee's work, I have introduced the Random Forest machine learning algorithm. Recent studies (Dewi & Imah, 2020; Qureshi et al., 2023) have demonstrated that Random Forest is more accurate than the decision tree classifier used by Lee. This addition aims to contribute to the ongoing progress in this research field.

## Operational Measures:
* **Variable**: In the overall research framework, the X variable represents the data sourced from CHILDES, comprising distinct text-based inputs from children with Specific Language Impairment (SLI), Autism Spectrum Disorder (ASD), or Typical Development (TD). The Y variable corresponds to the accuracy results generated by the algorithms selected by Lee. Now, in my research, as I introduce the evaluation of the entire research output by incorporating the Random Forest Algorithm into Lee's study, the X variable becomes the Random Forest Algorithm itself. The Y variable remains as the accuracy results yielded by the algorithms, facilitating a comparison of the changes in prediction accuracies with and without the inclusion of the Random Forest Algorithm.
* **Data Type**: The research utilizes cross-sectional data sourced from text-based transcripts within the CHILDES database. This data is specifically recorded in the context of children with Specific Language Impairment (SLI), Autism Spectrum Disorder (ASD), or Typical Development (TD) being prompted to retell a story to an adult.

## Hypothesis Development:
* **Prediction Hypothesis**: The integration of the Random Forest algorithm would not only alter the original ranking, resulting in it being the most superior among all, but also show unexpected finding about the detection of SLI/ASD/TD.
* **Justification**:As discussed in the literature review, the efficacy of the Random Forest algorithm in classifying Specific Language Impairment (SLI) and Autism Spectrum Disorder (ASD) stands out, demonstrating superior efficiency in the language impairment classification process. Additionally, Dewi and Imah's 2020 research emphasizes the Random Forest algorithm's superiority, stating that, 'based on specificity and sensitivity values, the Random Forest algorithm with full features is the optimal choice for classifying ASD in children and adolescents' (Dewi & Imah, 2020, pg. 152). This prompts my curiosity to explore whether Random Forest can not only address the challenges identified in Lee's study but also surpass the performance of Support Vector Machine (SVM), which was the most consistent and highest-performing machine learning algorithm in Lee's research, boasting an accuracy score of 87% +/- 3% (Lee, 2016, pg. 32).
* **Machine Learning Algorithm Selection**: As stated above with the reasonings, Random Forest is the chosen algorithm.

![](/Method/predictionMethod.png)

# The Machine Learning Workflow

## Model Development:
* **Data Processing**: The idea of NLP is that we are allowing the computer to break down the sentence by tokenization – the process of converting a sequence of text into smaller parts, known as tokens – and part-of-speech tagging (POS) to analyze the semantics and associate with a feature to distinguish between TD, ASD, or SLI children. Such a method would allow NLP to be executed to measure such as the mean length of utterance, total number of words, and even sentence complexity for intelligence and more. *As a common trait, many features are usually employed to detect LI in children, and feature with algorithm enhances the precision (Lee, 2016, pg. 6). With supervised classification, “detecting patterns is central to NLP as these patterns usually hold new meaning that can be derived from a sentence” (Lee, 2016, pg. 6). As for this research, Lee was using supervised classification, which means after NLP finds the features, the training was done under supervision to teach what is true to generate models and the corresponding feature sets to complete the prediction phase using the MLs.

| Step               | Description                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------------------- |
| **1. Feature Selection** | Choosing which features will be used to find patterns (NLP).                                   |
| **2. Training**         | Supervised Classification: The model is trained using pairs of labels and feature sets and corpa.              |
| **3. Prediction**       | The model uses these learned patterns to predict labels for new inputs.                             |

_In the context of a supervised classifier, "corpora" refers to a collection of data used for training the classifier. This dataset includes both the input data and their corresponding correct labels._

## Result Presentation
* **Training and Testing**: 
During the feature measurement phase, the program processes cleaned datasets of child text corpora, systematically enumerating various features. The ensuing section comprehensively outlines this array of features. These features are organized into an array format, with corresponding dataset labels appended, creating a structure of n samples by n features. This phase readies the data for subsequent stages (Lee, 2016, pg. 12).

The subsequent phase of the program is the training phase. In this stage, machine learners are provided with the measured features and their corresponding labels as inputs. The machine learner endeavors to categorize the labels based on the significance of each feature within the dataset during the training phase. Initially, all calculated features are utilized in the first round of training and prediction. Following this initial round, the program identifies the most indicative features, generating a refined set. Subsequent training and prediction phases then employ this smaller set of more indicative features, with the results being reported (Lee, 2016, pg. 12).

In all, for the training and testing, "70% of the samples will be used to train and test the machine learner. The remaining 30% would be for actual predictions (Lee, 2016, pg. 18)".

## Model Evaluation
Concerning data visualization, I will utilize a confusion matrix and KNN clustering to compare the outcomes of each machine learning algorithm both before and after feature extraction. This approach aims to thoroughly assess the effectiveness of Random Forest in comparison to the other algorithms.

![](/Method/machieneMethod.png)

## Citation

Dewi, E. S., & Imah, E. M. (2020). Comparison of machine learning algorithms for Autism Spectrum Disorder Classification. Proceedings of the International Joint Conference on Science and Engineering (IJCSE 2020). https://doi.org/10.2991/aer.k.201124.028 

Lee, Z. K. J. (2016). Use of Natural Language Processing and Machine Learning Techniques to Clinically Assess Children's Autism Spectrum Disorder and Specific Language Impairment. 

Qureshi, M. S., Qureshi, M. B., Asghar, J., Alam, F., & Aljarbouh, A. (2023). Prediction and analysis of Autism Spectrum Disorder Using Machine Learning Techniques. Journal of Healthcare Engineering, 2023, 1–10. https://doi.org/10.1155/2023/4853800 

