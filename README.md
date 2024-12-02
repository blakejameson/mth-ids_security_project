# MTH-IDS Security Project Group 9
### Participants
* Blake Jameson
* Noah Sadeghi
* Rigo Lizaola
* Ramiro Ramirez

# Description
This project focuses on evaluating and enhancing the performance of an Intrusion Detection System (IDS) by introducing new types of attacks into the dataset used for its initial testing. The primary objective is to determine if the IDS remains effective when subjected to a broader range of threats beyond those in its original training data.

To achieve this, we utilized publicly available datasets, which contain labeled network traffic data with various attack types (e.g., DoS, DDoS, Brute Force, Port Scanning). We merged these datasets, ensuring the resulting dataset maintains the same structure and feature alignment as the one used in the original research. By combining attack types from different sources, we introduced new malicious traffic patterns to evaluate the IDS under more challenging conditions.

# Goals
* Dataset Integration and Enhancement:
  * Combine different publicly available datasets to create a comprehensive dataset with a variety of attack types and nsure the merged dataset maintains proportionality across attack types and normal traffic to reflect real-world scenarios.

* Model Evaluation:
  * Train the IDS on the enhanced dataset and evaluate its performance using metrics like accuracy, precision, and F1-score, as well as identify if the IDS can generalize well to previously unseen or rare attack types.

* Reproducibility:
  * Provide documentation to ensure reproducibility of results with a fixed randomized seed.

* Real-World Variability:
  * Assess the robustness of the IDS by testing it against datasets with real-world variability, accounting for challenges like new attack patterns.

# Machine Learning Models
This research makes use of 4 models that were likely chosen because they are either ensemble-based or tree-based models that have unique strengths for handling classification tasks, particularly in intrusion detection systems.
* Decision Tree
  * Decision trees are interpretable and can reveal how decisions are made, making them useful for understanding how the IDS distinguishes between benign (normal) traffic and different types of attacks.

* Random Forest
  *  Random forest is an ensemble method that builds multiple decision trees during training and combines their outputs to improve performance and reduce overfitting. It increases the robustness of predictions by averaging multiple trees, making it less likely to overfit compared to a single decision tree.

* Extra Trees
  * Similar to random forests, extra trees create an ensemble of decision trees. However, the splits in extra trees are chosen randomly rather than being optimized. Random splits add more diversity to the model and help in reducing overfitting further.

* XGBoost
  * XGBoost is a gradient boosting algorithm that builds trees sequentially, where each tree corrects the errors made by the previous ones. It optimizes a loss function using gradient descent. It works well with unbalanced datasets and can capture complex patterns, which are common in network traffic data used in IDS.
