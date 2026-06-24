# malicious-prompt-detection

LLM safety classifier on the MPDD dataset using TF-IDF feature engineering
and multiple classifiers with GridSearchCV and 5-fold cross-validation.

## Files Included

- malicious_prompt_detection.ipynb - end-to-end notebook with EDA, modeling, and evaluation
- project_report.pdf - full project report
- dataset/MPDD.csv - main dataset (balanced, 50/50 malicious vs benign)
- dataset/jailbreak_prompts.csv - jailbreak prompt samples
- dataset/malicous_deepset.csv - malicious prompt samples
- dataset/malignant.csv - malignant prompt samples

Note: forbidden_question_set_df.csv (390MB), predictionguard_df.csv (113MB),
and question_pairs_dataset.csv (58MB) not included due to size.

## Techniques Used

- Text preprocessing and cleaning
- TF-IDF vectorization with unigrams and bigrams (max 20,000 features)
- Full EDA - class balance, prompt length, word count, point-biserial correlation
- Four classifiers with GridSearchCV and 5-fold cross-validation:
  - Multinomial Naive Bayes
  - Logistic Regression
  - Linear SVM
  - LightGBM (Gradient Boosting)
- Overfitting analysis and regularization tuning for each model

## Libraries

pandas, numpy, scikit-learn, lightgbm, matplotlib, seaborn

## Goal

To classify whether a prompt sent to an LLM is malicious or benign,
exploring how classical NLP features perform on LLM safety tasks.
