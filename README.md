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

# Types of Attacks

In this project, we focused on analyzing and detecting various types of attacks using an enhanced dataset that combined the CICIDS2017 and CICIDS2019 datasets. These datasets target different vulnerabilities in networks and simulate real-world scenarios. By integrating both datasets, we expanded the diversity of attack types to evaluate the IDS against a broader range of threats. Below are the attack categories studied:


1. **Denial of Service (DoS):**
   - These attacks aim to overwhelm a network or system, making it unavailable to legitimate users.
   - **Subcategories:**
     - **DoS GoldenEye**
     - **DoS Hulk**
     - **DoS Slowloris**
     - **DoS Slow-httptest**

2. **Distributed Denial of Service (DDoS):**
   - A coordinated attack involving multiple compromised systems targeting a single network or server.
   - **Subcategories:**
     - **DDoS DNS**
     - **DDoS LDAP**
     - **DDoS MSSQL**
     - **DDoS NetBIOS**
     - **DDoS UDP**

3. **Port Scanning:**
   - A reconnaissance technique used to find open ports and services running on a network.
   - **Attack Type:** Sniffing.

4. **Brute Force Attacks:**
   - An attack method to gain unauthorized access by systematically trying combinations of usernames and passwords.
   - **Subcategories:**
     - **SSH-Patator**
     - **FTP-Patator**

5. **Web Attacks:**
   - Exploits targeting web applications, typically involving malicious HTTP requests.
   - **Subcategories:**
     - **Web Attack – Brute Force**
     - **Web Attack – SQL Injection**
     - **Web Attack – XSS (Cross-Site Scripting)**

6. **Infiltration:**
   - A sophisticated attack where an intruder gains access to a network and remains undetected.

7. **Botnet:**
   - A network of infected computers controlled remotely to perform coordinated malicious activities.

8. **Benign Traffic:**
   - Normal network traffic used to simulate legitimate user behavior and ensure a balanced dataset.

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

# Foundational Research
"Data-Driven Intrusion Detection for Intelligent Internet of Vehicles: A Deep Convolutional Neural Network-Based Method" by Laisen Nie, Zhaolong Ning, Xiaojie Wang, Xiping Hu, Jun Cheng, and Yongkang Li (2020).

This seminal work employs a Deep Convolutional Neural Network (CNN) to analyze link load behaviors of Road Side Units (RSUs) in the IoV, effectively detecting intrusions by identifying irregular traffic flow patterns. The methodology provides a robust framework for understanding and mitigating cyber threats in vehicular networks.

Influence on this project:
  * **Methodology Adoption**: The use of deep learning techniques for intrusion detection in IoV environments has been instrumental in shaping our approach.
  * **Analytical Framework**: The analysis of link load behaviors as indicators of potential intrusions has informed our data processing strategies.

Contemporary Piece:
"Intrusion Detection System for Cyberattacks in the Internet of Vehicles Environment" by Mohamed Selim Korium, Mohamed Saber, Alexander Beattie, Arun Narayanan, Subham Sahoo, and Pedro H.J. Nardelli (2024).

This recent study introduces a machine learning-based intrusion detection system tailored for the IoV environment, capable of identifying cyberattacks such as Denial-of-Service (DoS), Distributed Denial-of-Service (DDoS), and Brute Force attacks. It emphasizes data preprocessing, feature selection, and model optimization to enhance detection accuracy and efficiency.

Influence on this project:
  * **Advanced Techniques**: Incorporation of sophisticated data preprocessing and feature selection methods to improve detection performance.
  * **Model Optimization**: Application of hyperparameter optimization to refine machine learning models, reducing overfitting and enhancing generalization.

# How To Run

The first step is to install a version of Python that is 3.10 or later. While working on the project, some of us received warnings from certain libraries with utilizing a version prior to Python3.10.

Depending on your OS and package manager, you will have commands to install an adequate Python version.

After having Python3.10 or later installed, you will create a virtual environment. You may do so through the commmand:

`python3 -m venv .venv` 

Another likely option is that your IDE comes equipped with the ability to create a virtual environment.

After creating a virtaul environment, make sure it is activated with the command:

`source .venv/bin/activate`

Another option would be to utilize your IDE to select your virtual environment.

Now with your virtual environment activated, enter the command:

`pip3 install -r requirements.txt` to install all neccesary packages.

With all packages installed, click on the file titled 'MTH_IDS_IoTJ_updated.ipynb'. Click 'Select Kernel', then click 'Python Environments', then click on the .venv that it recommends.

You are now able to go ahead and run the file. You can either click on the option 'Run All' or individually click on the run button to the left of the cell. Something to note when using this file is that the commands should be run consecutively as opposed to clicking cells lower then cells higher.


