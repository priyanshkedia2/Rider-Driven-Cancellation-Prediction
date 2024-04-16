In tackling the challenge of predicting rider-driven cancellations before they occur, we encountered skewed data riddled with NaN values. To address this, we applied the Progressive KNN method, as discussed on Kaggle, which effectively filled in the missing values. With a diminished feature set post-cleanup, we augmented it by introducing additional features, such as the time gaps between order, allotment, and acceptance, as well as indicators like day of the week, hour of the day, and a boolean flag for the start of the month. This augmentation significantly improved our model's roc_auc by 0.95, as detailed in the 'rider-pred-data-cleaning.ipynb' notebook.

Despite these enhancements, our initial models—XGBClassifier, CatboostClassifier, KNNClassifier—yielded roc_auc scores below 0.65. Seeking improvement, we turned to AutoXGB, which boosted our leaderboard standing to 0.77. Attempts to mitigate data skewness through SMOTE proved counterproductive, as it led to overfitting, with roc_auc scores of 0.91 in validation and 0.7 on the leaderboard.

In a last-ditch effort, we experimented with stacking approximately 20 AutoXGB models, yet this approach failed to yield desired results, and time constraints prevented us from revisiting it.
