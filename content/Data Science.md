# 1. Data Science

> A multidisciplinary field that involves problem solving by getting knowledge from data. 

It uses techniques from various disciplines, including mathematics, statistics, and computer science. The main goal is to solve problems using data, often through data analysis and machine learning. Data science aims to identify patterns and generate insights for decision-making across various industries. 

**Data Scientists** --> Professionals with a diverse skill set who can get knowledge and insights from data. They are experts in various areas like programming, databases, algorithms, mathematics, and statistics.
* **Skills** --> They need a mix of quantitative, technical, collaborative, and skeptical skills. They require expertise in areas like mathematics, algorithms, statistics, programming, infrastructure management, hypothesis creation, teamwork, and communication. Different types of data scientists specialize in various aspects of the field.
*   **Applications** --> Many fields, including medical diagnosis, customer segmentation, fraud detection, natural language processing, and image recognition.

## 1.1. Big Data
> Big data is characterized by **the 3 Vs** (high volume, velocity, and variety), making traditional data processing methods inadequate. It requires innovative and cost-effective information processing techniques for extracting valuable insights. 

Data can be:
1. **Structured Data** --> A predefined format and structure. Examples: CSV files.
2. **Semi-Structured Data** -->  A partially defined format, with tags, allowing for parsing and extraction. Examples: XML files.
*   **Quasi-Structured Data** --> This type has irregular formatting that can be structured with effort. Examples include clickstream data and log files.
*   **Unstructured data:** This type has no inherent structure and requires specialized techniques for analysis. Text documents, images, audio, and video files fall into this category.



**Process of Data Science**
1.   *Data Collection and Understanding*
2.   *Data Cleaning and Formatting*
3.   *Data Analysis*
4.   *Problem Identification*
5.   *Solution Development Using Data*

**Data Analysis** --> Data analysis aims to uncover useful information from data using techniques like statistics and algorithms.

**Data Scientists** --> They possess a blend of skills from multiple areas. A good data scientist has proficiency in data analysis and machine learning.
- **Skills**: *Quantitative Skills*, *Technical Skills*, *Skeptical Mindset*, *Collaborative Abilities*
* **Types**: *Data Preparer*, *Data Analyzer* etc..

> **Business Intelligence** --> Best practices that help getting access to (and analysis of) information to improve decision-making and performance.

> **Big Data** -> Big data consists of high-volume, high-velocity, and/or high-variety information assets that necessitate cost-effective and innovative information processing methods.

*The Three Vs of Big Data* --> **Volume** (Size of data), **Velocity** (Speed of generation and processing of data) and **Variety** (Diversity of data).
	1.   *Structured Data*: Data with defined types and structure, like CSVs.
	2.   *Semi-Structured Data*: Textual data with a parseable pattern, like XML files.
	3.   *Quasi-Structured Data*: Textual data with irregular formats that can be formatted with effort, like clickstream data.
	4.   *Unstructured Data*: Data without inherent structure and often in multiple formats, such as websites and videos.

> [!Question] What to do with Data?
> 1. Aggregation and Statistics: Data warehousing and OLAP (Online Analytical Processing).
 2. Indexing, Searching, and Querying: Keyword-based search and pattern matching (XML/RDF).
 > 2. Knowledge Discovery: Data mining and statistical modeling.

*   **Real-Life Examples of Data Science** -> Understanding Consumer Behavior and Political Campaigns.

# 2. Machine Learning (ML)

*   **What is Machine Learning?** Machine learning is a subfield of artificial intelligence that enables computers to learn from data without explicit programming. ML algorithms identify patterns and build models to make predictions or decisions. It encompasses various techniques like supervised learning, unsupervised learning, and reinforcement learning.
*   **Machine Learning Workflow:**
    *   **Training Phase:** In this phase, the ML algorithm is trained on a dataset to build a model. The algorithm learns from the data and adjusts its parameters to minimize errors and improve accuracy.
    *   **Test Phase:** The trained model is tested on a separate, unseen dataset to assess its performance. This helps to evaluate how well the model generalizes to new data. 
    *   **Evaluation Phase:**  The model's performance is evaluated using specific metrics to quantify its accuracy and effectiveness. Common metrics include accuracy, precision, recall, and F1-score for classification problems, and RMSE and MAE for regression problems. 
*   **Types of Machine Learning:**
    *   **Supervised Learning:**  This type uses labeled data to train an algorithm to predict outcomes or classify data. Common applications include image classification, spam detection, and fraud detection.
        *   **Classification:**  This task involves categorizing data into predefined classes. Examples include binary classification (two classes) and multi-class classification (more than two classes). Algorithms for classification include logistic regression, decision trees, support vector machines, and neural networks.
        *   **Regression:** This task involves predicting a continuous output variable based on input features. Common examples include predicting house prices, stock prices, or sales figures. Algorithms for regression include linear regression, polynomial regression, and support vector regression.
    *   **Unsupervised Learning:** This type uses unlabeled data to discover hidden patterns and structures in the data. It's often used for clustering similar data points, reducing data dimensionality, or detecting anomalies. Examples include customer segmentation, market basket analysis, and anomaly detection.
        *   **Clustering:**  This task involves grouping data points based on their similarity.  The goal is to create clusters where data points within the same cluster are more similar to each other than to those in other clusters. Algorithms for clustering include k-means clustering, hierarchical clustering, and DBSCAN.
    *   **Reinforcement Learning:** This type involves an agent interacting with an environment and learning through trial and error. The agent receives rewards for desirable actions and penalties for undesirable actions, and its goal is to maximize its cumulative reward. This type of learning is common in robotics, game playing, and control systems. 
*   **Key Algorithms:**  
    *   **Logistic Regression:** A linear model used for binary classification. It predicts the probability of a data point belonging to a specific class.
    *   **Decision Trees:** A tree-like structure where internal nodes represent decision rules and leaf nodes represent outcomes. It's used for both classification and regression tasks. 
        *   **Rule Induction:**  This involves extracting rules from a decision tree to create a set of "if-then" rules for classification. 
    *   **k-Nearest Neighbors (kNN):**  A non-parametric algorithm that classifies data points based on the majority class of their k-nearest neighbors. It relies on a distance metric to determine proximity.
    *   **Naive Bayes:** A probabilistic classifier based on Bayes' theorem, assuming feature independence. It's widely used in text classification and spam filtering.
    *   **Neural Networks:**  A network of interconnected nodes (neurons) that can learn complex patterns from data. Deep learning utilizes neural networks with multiple layers to achieve higher accuracy. Neural networks are powerful tools for various tasks, including image recognition, speech recognition, and natural language processing.
    *   **Support Vector Machines (SVM):** An algorithm that finds the optimal hyperplane to separate classes in a high-dimensional space. It's used for both classification and regression tasks.

Machine learning involves the creation and utilization of models that learn from data. Key components include:
	*   *Data*: Any measurable or recordable information.
	*   *Model*:  A representation of the mathematical relationship between variables.
	*   *Evaluation*: Assessing the effectiveness of the model.

*   **Types of Machine Learning**
    *   **Regression**: Predicting continuous values (e.g., predicting house prices).
    *   **Classification**:  Categorizing data into predefined classes (e.g., classifying emails as spam or not spam).
    *   **Clustering**: Grouping data points based on similarities without predefined labels (e.g., customer segmentation based on purchasing behavior).
*   **Machine Learning Workflow**
    *   The workflow consists of three phases:
        *   **Training Phase**: The model learns patterns from the training data.
        *   **Test Phase**: The trained model is applied to unseen test data to make predictions.
        *   **Evaluation Phase**: The model's performance is assessed by comparing predictions to actual values using metrics like accuracy, precision, or error measures.

> [!Question] Traditional CS vs. Machine Learning
> In traditional computer science, programs are written to process data and produce output. In machine learning, the program learns from the data to generate output, essentially "programming itself.

*   **Data Structures**
	*   **Set**: Used for storing unique, unordered data without duplicates.
	*   **Array**: Suitable for storing large, homogeneous, numerical data efficiently.
	*   **List**: A general-purpose structure for ordered data that can contain duplicates. 

## 2.1. Regression
A supervised learning technique for analyzing and predicting relationships between variables. It aims to understand how changes in independent variables affect the dependent variable.
*   *Dependent Variable*:  The outcome variable being predicted. (Target)
*   *Independent Variables*:  The predictor variables that influence the dependent variable. (Features)
*   *Coefficients*: Quantify the relationship between independent and dependent variables.
*   *Error Term* (ϵ): Represents the unexplained variation in the model.
#### Types of Regression
1.   **Linear Regression** -> Models the relationship between variables using a straight line.
	1. *Simple Linear Regression*: Involves one independent variable.
	2. *Multiple Linear Regression*:  Involves multiple independent variables.
2.   **Logistic Regression** -> Used for predicting categorical outcomes, often binary (yes/no).
3.   **Polynomial Regression** -> Extends linear regression to model non-linear relationships using polynomial terms.
4.   **Ridge and Lasso Regression** -> Regularized linear regression methods that prevent overfitting.
	1. *Ridge Regression*: Penalizes large coefficients.
	2. *Lasso Regression*: Can shrink coefficients to zero, helping with feature selection.
5.   **Support Vector Regression (SVR)** -> Adapts Support Vector Machines for regression tasks, finding an optimal hyperplane to fit data.
6.   **Decision Tree and Random Forest Regression** -> Tree-based methods for regression.
	1. *Decision Trees*: Creates a tree-like model for predictions.
	2. *Random Forest*: An ensemble of decision trees that improves prediction robustness.
#### Key Metrics for Regression Evaluation
1. **R-squared (R<sup>2</sup>)**: Measures the proportion of variance in the dependent variable explained by the model. Higher values (closer to 1) indicate a better fit.
2. **Mean Squared Error (MSE)**: The average of squared differences between actual and predicted values. Lower MSE indicates better performance.
3. **Root Mean Squared Error (RMSE)**: The square root of MSE, providing error in the same units as the dependent variable. Sensitive to large errors due to squaring.
4. **Mean Absolute Error (MAE)**: The average of absolute differences between actual and predicted values, offering an interpretable error measure. Less sensitive to outliers, providing a more robust error measure. 

>Applications of Regression -> Predicting Prices, Risk Assessment, Medical Research, Marketing etc.

*   **Training**: Finding the best-fitting line that minimizes the error between predicted and actual house prices.
*   **Prediction**:  Using the trained model (equation of the line) to predict prices for new houses based on their features.
*   **Model Complexity and Evaluation**: More complex models (e.g., higher-order polynomials) may fit the training data perfectly but can lead to overfitting, where the model performs poorly on unseen data. Evaluation metrics like RMSE and MAE are used to assess model performance on test data, helping to choose the best model that generalizes well to new data.
*   **Training Error vs. Test Error**
    *   Training error -> the error on the data used to train the model.
    *   Test error -> the error on a separate dataset not used for training, which reflects the model's ability to generalize.

## 2.2. Classification

*   **Definition**: Classification is a supervised learning technique used to categorize data into predefined classes.
*   **Objective**: Predict the class or category of new data based on patterns learned from labeled data.

#### Types of Classification
*   **Binary Classification**: Involves two classes (e.g., YES/NO, MALE/FEMALE, SPAM/NOT SPAM).
*   **Multi-Class Classification**: Involves more than two classes (e.g., handwritten digit recognition (0-9)).
*   **Multi-Label Classification**: Assigns multiple labels to each instance (e.g., tagging a social media post with multiple categories).
##### Classification Algorithms
1. **Logistic Regression** -> A linear model for binary classification.
    *   **Example**: Predicting whether a patient has a disease based on features like age and weight.
2. **Decision Trees** -> A tree-like structure where Internal nodes represent decision rules and Leaf nodes represent outcomes.
    *   **Example**:  Classifying if a customer will churn based on their service usage.
	*   **Concepts**:
	    *   *Predictors/Attributes*:  Features used to make decisions.
	    *   *Target/Class*:  The outcome to be predicted.
	    *   *Tree Split*: Dividing data based on attribute values.
	*   **Impurity Measures**:
		*   *Entropy*: Measures the disorder or randomness in a set.
		*   *Gini Impurity*: Another measure of impurity.
		*   *Misclassification Error*: The rate of incorrect classifications.
		*   Splits aim to reduce impurity in child nodes, making them more homogeneous.
	*   **Rule Induction** -> Extracting rules from decision trees to represent classification logic.
3. **k-Nearest Neighbors (kNN)** -> Classifies data points based on the majority class of their k-nearest neighbors.
    *   **Example**: Predicting tumor type (malignant/benign) based on similar cases.
	*   **Measures of Proximity**:
	    *   *Distance*: Commonly used metric (e.g., Euclidean distance).
	    *   *Correlation Similarity*: Measures the linear relationship between data points.
	    *   *Simple Matching Coefficient*:  Counts the number of matching attributes.
	    *   *Jaccard Similarity*:  Measures similarity based on the ratio of shared attributes to the total number of attributes.
	    *   *Cosine Similarity*: Measures similarity based on the angle between data point vectors. 
4. **Naive Bayes** -> A probabilistic classifier based on Bayes' theorem, assuming feature independence.
    *   **Example**: Classifying document categories (text classification).
	*   **Concepts**:
	    *   *Class Conditional Probability*: Probability of observing features given a class.
	    *   *Posterior Probability*: Probability of a class given the observed features.
	    *   *Prior Probability*: Initial probability of a class before observing features.
	*   **Issues**:
	    *   *Incomplete Training Set*: Addressed using Laplace correction.
	    *   *Continuous Numeric Attributes*: Handle using probability density functions.
	    *   *Attribute Independence Assumption*:  May need to remove correlated attributes.
5. **Neural Networks** -> Inspired by the human brain, neural networks consist of interconnected nodes (neurons) that process and transmit information. They can learn complex patterns from data. 
6. **Support Vector Machines (SVM)** -> Finds the optimal hyperplane to separate classes in a high-dimensional space.
    *   **Example**: Classifying emails as work, personal, or spam.
	*   **Concepts**:
	    *   *Boundary*: The decision boundary separating classes.
	    *   *Margin*: The distance between the boundary and the closest data points.
	    *   *Kernel Trick*:  Transforms data to higher dimensions to improve separability.

#### Key Metrics for Classification Evaluation:
1.   **Precision**:  Measures the accuracy of positive predictions.
2.   **Recall**:  Measures the ability to identify all positive instances.
3.   **F1-Score**: A harmonic mean of precision and recall, providing a balanced performance measure.
4.   **Confusion Matrix**:  A table that summarizes classification results, showing true positives, true negatives, false positives, and false negatives.

> Applications of Classification -> Medical Diagnosis, Customer Segmentation, Fraud Detection, Natural Language Processing (NLP), Image Recognition.

## 2.3. Clustering
An unsupervised learning technique that organizes data into groups (clusters) based on similarity. The goal is to achieve high similarity within clusters and low similarity between clusters.
*   **Key Difference from Classification**: Clustering discovers labels directly from data without predefined classes or labeled examples.
*   **Concept of Similarity**
    *   Similarity measures the strength of the relationship between data items, indicating how alike they are.
    *   Clustering relies on similarity measures to group similar data objects together. 
*   **Distance Measures**
    *   Distance measures are often used to quantify similarity.
	*   **Euclidean Distance** -> Straight-line distance between points.
	*   **Manhattan Distance** ->  Distance calculated as the sum of absolute differences along each dimension.
#### Types of Clustering
*   **Partitional Algorithms**: Create partitions and evaluate them based on a criterion.
*   **Hierarchical Algorithms**:  Build a hierarchical decomposition of objects based on a criterion. 
##### Clustering Algorithms
**K-Means Algorithm**, A popular partitional clustering algorithm.
1.  Decide on the number of clusters, *k*.
2.  Initialize *k* cluster centers (randomly or using a more informed approach).
3.  Assign objects to their nearest cluster center.
4.  Recalculate cluster centers based on the current object assignments.
5.  Repeat steps 3 and 4 until convergence (no objects change clusters).

*   **Strengths**:
	*   Relatively efficient.
	*   Easy to implement. 
*   **Weaknesses**:
	*   The concept of "mean" needs to be defined, making it unsuitable for categorical data.
	*   It's a heuristic (approximation) that can get stuck in local optima.
	*   The number of clusters (*k*) needs to be specified in advance.
	*   Sensitive to noisy data and outliers.
	*   Tends to find spherical clusters and may not perform well with other cluster shapes. 

*   **Elbow Method** -> Use an objective function (e.g., within-cluster sum of squares) to evaluate clustering for different *k* values. Plot the objective function against *k* and look for an "elbow" point, which suggests a suitable number of clusters. 

> Applications of Clustering -> EDA (Exploratory Data Analysis), Color Compression, Finding Distribution Centers, Making Recommendations.

**Clustering Evaluation** -> A good partitioning algorithm aims to minimize an objective function that quantifies the quality of the clustering.

# 3. Exploratory Data Analysis (EDA)

*   **Purpose of EDA:** EDA involves exploring and analyzing a dataset to understand its characteristics, patterns, and potential issues. It helps to generate hypotheses, identify data quality problems, and inform subsequent modeling decisions. Techniques like summary statistics, data visualization, and correlation analysis are employed in EDA. 
*   **Data Sources:** Data for EDA can be obtained from various sources, including internal databases, external datasets, web scraping, and APIs. Understanding the data source and its limitations is essential for accurate analysis.
*   **Data Pre-processing:** Raw data often needs pre-processing before analysis. This includes:
    *   **Data Parsing and Formatting:**  Converting data into a usable format for analysis. This involves structuring data into tables, arrays, or other suitable representations.
    *   **Data Profiling:**  This step involves assessing the quality and quantity of data, identifying missing values, outliers, and data inconsistencies. 
    *   **Data Cleaning:**  This involves addressing data quality issues, such as handling missing values, correcting errors, removing duplicates, and transforming data types. 
    *   **Feature Engineering:** Creating new features from existing ones to enhance the performance of machine learning models. This can involve combining variables, creating interaction terms, or applying transformations.
*   **Data Visualization Techniques:** Visualization is a crucial aspect of EDA. It allows for understanding data patterns, relationships, and distributions. Common visualization techniques include:
1.   *Distribution Visualization* --> Shows how a variable is distributed over a range of values (e.g., histograms).
2.   **Relationship Visualization**: Depicts the relationship between two or more variables (e.g., scatter plots).
3.   **Comparison Visualization**: Compares trends in different variables or datasets (e.g., multiple histograms, box plots).
4.   **Composition Visualization**:  Illustrates the breakdown of a dataset into subgroups (e.g., pie charts, stacked area graphs).


**Sources of Data**
- Internal Sources (Business-centric data or Scientific experimental data)
- External Sources (Public government databases or Stock market data)

**Collected Data** -> Data gathered specifically for the project.
**Online Data** -> Data obtained from APIs (e.g., Google Maps, Facebook, Twitter) or Web scraping is used to extract data from websites.

**Variables and Data Types** -> Different types of variables and data types need to be considered during EDA.

**Common Data Issues**
1.   *Missing values*: Need to be handled appropriately, either by imputation or other methods.
2.   *Wrong values*: Require detection and correction to ensure data accuracy.
3.   *Messy format/representation*: Data may need restructuring or cleaning for analysis.

> Causes of messiness -> Variables stored in both rows and columns, multiple features in a single column, etc.
## 3.1. Data Pre-processing
*   The goal is to prepare data for analysis and machine learning, including:
	1.   Data parsing and formatting
	2.   Data profiling to assess data quality and quantity
	3.   Data cleaning
	4.   Data engineering tasks like outlier detection, feature engineering, and data augmentation.

**Population vs. Sample Data**
*   *Population*: The entire set of objects or events under study.
*   *Sample*: A representative subset of the population.
*   Samples are often used due to the impracticality of collecting or analyzing the entire population data.
*   **Techniques**:
    *   **Exploring Individual Variables**:
        *   Summary statistics (mean, median, mode)
        *   Measures of spread (range, variance, standard deviation)
        *   Distribution analysis (histograms)
    *   **Assessing Interactions Between Variables**:
        *   Correlation analysis
        *   Analysis of Variance (ANOVA)
    *   **Multidimensional Data Exploration**:
        *   Clustering
        *   Dimensionality reduction techniques (e.g., Principal Component Analysis - PCA)

Statistical Terms
**Summary Statistics** -> The choice between mean and median depends on data distribution and the presence of outliers. The mean is sensitive to outliers.
*   *Mean*: The average value.
*   *Median*: The middle value when data is sorted.
*   *Mode*: The most frequent value.

**Measures of Spread** -> Understanding data spread is crucial for assessing data variability and potential outliers.
*   *Range*: The difference between the maximum and minimum values.
*   *Variance*: Measures how data points are spread out from the mean.
*   *Standard Deviation*: The square root of the variance.

## 3.2. Data Visualization
Data visualization complements summary statistics and provides a visual representation of data patterns and relationships.

Types of Data Visualization


Visualization Techniques
1.   **Histogram**: Used for visualizing the distribution of a single variable.
2.   **Scatter Plot**: Shows the relationship between two variables.
3.   **Box Plot**: Useful for comparing distributions, showing quartiles, median, outliers, and comparing a variable across groups.
4.   **Pie Chart**: Depicts the composition of a dataset, showing the proportion of each category.
5.   **Stacked Area Graph**:  Visualizes trends in composition over time.

> Color-coding can be used in visualizations to represent categorical variables.

*   **Multidimensional Visualization**
    *   3D visualizations can be used to explore relationships between three variables, but they are not always effective.

# 4. Model Evaluation
> Evaluating the performance of machine learning models is important to know their effectiveness and generalization ability.

Data is typically split into "training" and "test" sets to evaluate model performance on unseen data. 
*   **Evaluation Metrics:**
    *   **Classification Metrics:**
        *   **Precision:** Measures the proportion of correctly classified positive instances out of all instances predicted as positive.
        *   **Recall:** Measures the proportion of correctly classified positive instances out of all actual positive instances.
        *   **F1-score:**  A harmonic mean of precision and recall, providing a balanced measure of classification performance.
    *   **Regression Metrics:**
        *   **R-squared (R²):**  Indicates the proportion of variance in the dependent variable that is explained by the independent variables.
        *   **Mean Squared Error (MSE):**  Averages the squared differences between predicted and actual values.
        *   **Root Mean Squared Error (RMSE):**  The square root of MSE, providing an interpretable measure of error in the same units as the dependent variable. 
        *   **Mean Absolute Error (MAE):**  Averages the absolute differences between predicted and actual values. 
*   **Overfitting:** Occurs when a model learns the training data too well and fails to generalize to new data. Regularization techniques can help prevent overfitting.

# 5. Data Mining Process

*   **CRISP-DM (Cross-Industry Standard Process for Data Mining):** This widely used methodology provides a structured approach to data mining projects, encompassing the following phases:
    *   **Business Understanding:**  Clearly defining the business objectives, understanding the problem domain, and translating business goals into data mining goals.
    *   **Data Understanding:**  Collecting data from various sources, exploring data characteristics, identifying data quality issues, and verifying data relevance.
    *   **Data Preparation:** Transforming raw data into a suitable format for modeling. This involves data cleaning, handling missing values, feature engineering, and data integration.
    *   **Modeling:** Selecting and applying appropriate data mining algorithms, such as classification, regression, or clustering, and optimizing model parameters.
    *   **Evaluation:** Assessing the performance of the model against business objectives, considering various evaluation metrics, and validating model stability. 
    *   **Deployment:**  Integrating the model into operational systems, monitoring model performance, and ensuring the model meets business requirements.  

**CRISP-DM Process** (Cross-Industry Standard Process for Data Mining) is a widely used framework for data mining projects. 
*   **Stages of CRISP-DM**:
	*   *Business Understanding*: Defining the project objectives and requirements from a business perspective.
	*   *Data Understanding*:  Collecting, exploring, and assessing the quality of data.
	*   *Data Preparation*:  Cleaning, transforming, and preparing data for modeling.
	*   *Modeling*: Selecting and applying data mining algorithms to build models.
	*   *Evaluation*: Assessing the performance and validity of the models.
	*   *Deployment*: Implementing the models and integrating them into business processes.
*   **Five Stages of Data Mining**
    *   **Prior Knowledge**: Acquiring background information about the problem's objective, subject area, and available data.
    *   **Data Preparation**:  This stage involves:
        *   Data exploration to understand its characteristics.
        *   Data quality assessment and handling of missing values.
        *   Data type conversion and transformation as needed.
        *   Identification and handling of outliers.
        *   Feature selection to choose relevant variables.
        *   Data sampling if dealing with very large datasets.
    *   **Modeling**:
        *   Building a model using selected algorithms and training data.
        *   Splitting the data into training and test sets.
        *   Training the model on the training data and evaluating it on the test data.
        *   Selecting the best-performing model based on evaluation results.
    *   **Application**:
        *   Ensuring the model is ready for deployment in a production environment.
        *   Integrating the model into technical systems.
        *   Monitoring the model's response time and performance.
        *   Considering the need for remodeling as new data becomes available.
        *   Facilitating the assimilation of insights from the model into business processes.
    *   **Knowledge**: 
        *   Gaining posterior knowledge and insights derived from the data mining process.

# 6. Deep Learning
> A subfield of machine learning that utilizes artificial neural networks with multiple layers (deep neural networks) to model complex patterns and relationships in data. 

Inspired by the human brain, deep learning excels in tasks like image recognition, speech recognition, natural language processing, and machine translation.

*   **Key Concepts:** 
    *   **Feature Representation:**  Deep learning models automatically learn relevant features from raw data, reducing the need for manual feature engineering.
    *   **Representation Learning:** Deep learning models can learn hierarchical representations of data, where lower layers capture basic features and higher layers learn more complex abstractions. 
    *   **Sparse Coding:** A technique that represents data using a sparse set of basis functions, allowing for efficient data representation and capturing essential patterns. 
    *   **Virtuous Circle of AI:** AI products that collect data can be improved by using this data to train better models, leading to a cycle of continuous improvement. 
*   **Trends in Deep Learning:**
    *   **Learning from Tagged and Untagged Data:** Deep learning models can be trained using both supervised and unsupervised learning methods, leveraging both labeled and unlabeled data.
    *   **Bigger is Better:** Larger models with more layers and connections often achieve higher performance, but require significant computational resources.
    *   **GPUs:** Graphics Processing Units (GPUs) are essential for training large deep learning models due to their parallel processing capabilities.
*   **Applications:**
    *   **Speech Recognition:**  Deep learning models have significantly improved speech recognition accuracy, enabling applications like voice assistants and automatic transcription. Examples include Baidu Cool Box.
    *   **Image Recognition and Search:** Deep learning has revolutionized image recognition, leading to applications like object detection, image classification, and visual search engines. Examples include Baidu Eye.
    *   **Natural Language Processing:**  Deep learning models are being used for tasks like machine translation, sentiment analysis, text summarization, and question answering.
    *   **Recommendation Systems:** Deep learning techniques are employed to personalize recommendations in areas like e-commerce, entertainment, and news.

## 6.1. Neural Network Structure
> A machine learning model that makes decisions like a human brain. It uses processes that mimic the way biological neurons work together.

They are made up of "neurons" which are organized into "layers". Each connection between then has a "weight" (strength of the connection). When training is done, the weights are adjusted to decrease errors and increase model accuracy. 

*Key Characteristics* --> **Neurons**, **Layers**, **Input and Output**, **Learning**.

*Applications* --> Spam Detection, Information Retrieval, Recognition, Robotics, Recommendation Systems, Computer Vision Systems, Home Virtual Assistants.


> [!INFO] Motivation for Neural Networks
> They excel in **representation learning,** automatically extracting features from input data, unlike traditional machine learning approaches that rely on hand-crafted features.





It has led to significant advancements in various fields like computer vision, speech recognition, and natural language processing.
* One of the key factors driving the success of deep learning is the availability of large amounts of data. 
    * As the amount of data increases, the performance of deep learning algorithms tends to improve, creating a **virtuous circle of AI** where better products attract more users, generating more data, and further improving AI.
* **The "one learning algorithm" hypothesis** suggests that a single learning algorithm might be responsible for most of human intelligence. 
    * This hypothesis is supported by research showing that different areas of the brain, like the auditory and somatosensory cortex, can learn to process visual information.

### Key Applications of Deep Learning
* **Computer Vision:** 
    * Tasks include image labeling, object recognition (e.g., identifying a coffee mug), and scene understanding. 
    * Challenges in computer vision arise from the complexity of images and the difficulty in extracting meaningful features. 
* **Speech Recognition:** 
    * Involves converting spoken audio into text. 
    * Challenges include variability in speech patterns, background noise, and the need to extract relevant acoustic features. 
* **Web Search:** 
    * Deep learning is used to improve search results by understanding user intent, ranking web pages, and personalizing search experiences.
* **Image Search:** 
    * Deep learning algorithms can analyze images and retrieve relevant results based on image content, improving the accuracy and efficiency of image search engines.
* **Natural Language Processing:**
    * Deep learning is used for tasks like machine translation, sentiment analysis, text summarization, and dialogue systems.
* **Advertising and Recommendation Systems:** 
    * Deep learning helps personalize advertising and recommendations by understanding user preferences, behavior, and demographics.
* **Robotics:** 
    * Deep learning enables robots to perceive and interact with their environment, learn from experience, and perform complex tasks autonomously.

### Feature Representation and Learning
* **Feature representation** is crucial in machine learning, where raw data is transformed into a set of features that capture relevant information. 
    * For vision tasks, features like SIFT, Shape context, and GIST are used to describe image content. 
    * For audio, features like ZCR, spectrogram, MFCC, rolloff, and flux are extracted to represent sound characteristics. 
    * Text features include parsing results, named entities, stemming, part-of-speech tags, and co-reference information.
* Deep learning algorithms learn hierarchical feature representations, where simple features are combined to form more complex ones. 
    * **Sparse Coding** is an example where input images are represented as a weighted sum of a set of learned basis matrices. 
        * This allows for efficient representation of images using a sparse set of coefficients.
* Deep learning models can learn to detect specific objects or concepts, as demonstrated by the discovery of "face neurons" and "cat neurons" that selectively respond to faces and cats respectively.

### Supervised and Unsupervised Learning
* **Supervised learning** involves training models on labeled data, where each example is associated with a known output. 
    * The model learns to map input features to the correct output, allowing it to make predictions on unseen data.
* **Unsupervised learning** involves training models on unlabeled data, where the model learns to identify patterns and structure in the data without explicit guidance.
    * This type of learning is crucial for tasks where labeled data is scarce or expensive to obtain.

### Trends and Future Directions
* **Bigger is better:** Deep learning models with larger numbers of connections tend to perform better.
    * This has led to the development of massive neural networks like Google Brain, containing billions of connections.
* **Shift from supervised to unsupervised learning:** As deep learning matures, the focus is shifting towards unsupervised learning to leverage the vast amounts of unlabeled data available.
* **AI as a computer systems problem:** Building and training large-scale deep learning models requires significant computational resources.
    * This has led to the use of **GPUs (Graphics Processor Unit)** for faster training and inference.
* **Paradigm shifts in technology:** Deep learning is expected to revolutionize various technology areas, including computer vision, speech recognition, language understanding, advertising, personalization, and robotics.

### Discussion Points
* **Engineering vs. Data:** The performance of AI systems depends on both human ingenuity in designing algorithms and the availability of high-quality data.
    * While human ingenuity plays a significant role in the early stages of development, data and learning become increasingly important over time.

## Neural Networks

### History (Not Important)

1. 1945: The first programmable machine, ENIAC (Electronic Numerical Integrator and Computer), was created during World War II.
2. 1945-1950: Alan Turing proposed the **Turing Test**, which aimed to determine if a machine could exhibit intelligent behavior indistinguishable from a human.
3. 1956: A workshop at Dartmouth College marked the **birth of artificial intelligence (AI)**, focusing on problem-solving abilities typically associated with humans.
4. 1959: AI researcher Arthur Samuel coined the term **"machine learning,"** defining it as the field that enables computers to learn without explicit programming.
5. 1986: Neural networks with effective learning strategies emerged.

*   **Rises/Falls of Neural Network Popularity:**
	*   Neural networks have experienced multiple waves of popularity and decline.
	*   2012: **Wave 3**, the rise of **"deep learning,"** began.

*   **How Does a Machine Learn?**
    *   **General Idea:** An algorithm learns patterns from data to make predictions.
    *   **Types of Learning:**
        *   **Supervised Learning:** Identifies patterns by studying labeled data with expected outputs.
        *   **Unsupervised Learning:** Identifies patterns by observing data without labels.
    *   **Typical Algorithm Design:**
        *   Supervised learning tasks include:
            *   **Regression:** Predicting a continuous value.
            *   **Classification:** Predicting a discrete value.
        *   Unsupervised learning tasks include:
            *   **Clustering:** Grouping similar data points.
            *   **Anomaly Detection:** Identifying unusual data points.
        *   Models with increasing representational capacity are used in classification, ranging from linear equations to complex curves.
        *   Modern deep learning algorithms build upon techniques developed over the past 65 years.
# 7. Problems
# 8. Coding

> [!Error] In-case Sir gives coding in paper

## 8.1. Python's Libraries
1. **Numpy**: A fundamental package for numerical computing in Python, providing support for arrays, matrices, and a variety of mathematical functions.
2. **Pandas**: A powerful data manipulation and analysis library that offers data structures like DataFrames for handling structured data.
3. **Matplotlib**: A plotting library for creating static, animated, and interactive visualizations in Python.
4. **Scikit-Learn**: A machine learning library that provides simple and efficient tools for data mining and data analysis, built on NumPy, SciPy, and Matplotlib.
5. **Seaborn**: A statistical data visualization library based on Matplotlib that provides a high-level interface for drawing attractive and informative graphics.
### EDA in Pandas
- **Loading Data**: 
  ```python
  import pandas as pd
  df = pd.read_csv('data.csv')  # Load data from a CSV file
Basic Statistics:
Edit:
Data Science (Finals) - Jaish Khan.md
+38
-2
497
Preview
Apply
print(df.describe())  # Get a summary of statistics for numerical columns
Handling Missing Values:
Edit:
Data Science (Finals) - Jaish Khan.md
+38
-2
497
Preview
Apply
df.fillna(0, inplace=True)  # Replace missing values with 0
Making Charts
Line Chart:
Edit:
Data Science (Finals) - Jaish Khan.md
+38
-2
497
Preview
Apply
import matplotlib.pyplot as plt
plt.plot(df['Date'], df['Value'])
plt.title('Line Chart Example')
plt.xlabel('Date')
plt.ylabel('Value')
plt.show()
Bar Chart:
Edit:
Data Science (Finals) - Jaish Khan.md
+38
-2
497
Preview
Apply
df['Category'].value_counts().plot(kind='bar')
plt.title('Bar Chart Example')
plt.xlabel('Category')
plt.ylabel('Frequency')
plt.show()```

# Decision Tree --> Rules (Induction)

We have this decision tree
![[WeatherDecisionTree.excalidraw]]

To convert this into "Rules" go from left-to-right and write each of the branches:

1. If `Price < 1000` then **yes**
2. If `Price = 1000 AND Quality = good` then **yes**
3. If `Price = 1000 AND Quality = bad` then **no**
4. If `Price > 1000 AND Quality = good AND Premium = yes` then **yes**
5. If `Price > 1000 AND Quality = good AND Premium = no` then **no**
6. If `Price > 1000 AND Quality = bad` then **no**

# Rules (Induction) --> Decision Tree

We have these rules for this question **Should I watch a movie?**
1. If `Weekend = yes AND Exam = yes AND Preparation = yes` then **yes**
2. If `Weekend = yes AND Exam = yes AND Preparation = no` then **no**
3. If `Weekend = yes AND Exam = no` then **yes**
4. If `Weekend = no` then **no**

Just go line-by-line and draw each branch:
![[MovieDecisionTree.excalidraw]]

# Distance Calculation
There are two types of distances  

1. The Euclidean distance between two points $A(x_1, y_1)$ and $B(x_2, y_2)$ in a 2D space is the straight-line distance, calculated using the formula:
$$d_{\text{e}} = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$$​

**Example**: Points $A(1, 2)$ and $B(4, 6)$

$$
d_{e}=\sqrt{(4−1)^2+(6−2)^2}=\sqrt{32+42}=\sqrt{9+16}=\sqrt{25}=5
$$

2. The Manhattan distance between the same points $A(x_1, y_1)$ and $B(x_2, y_2$) is calculated as:
$$d_{\text{m}} = |x_2 - x_1| + |y_2 - y_1|$$

**Example**: Points $A(1, 2)$ and $B(4, 6)$

$$d_{\text{m}} = |4 - 1| + |6 - 2| = 3 + 4 = 7$$


# Choosing between Regression, Classification and Clustering

When do we choose each of these

|                        | Regression                            | Classification                                   | Clustering                                   |
| ---------------------- | ------------------------------------- | ------------------------------------------------ | -------------------------------------------- |
| When?                  | You have to predict a "number" value. | You have to separate data into "groups/classes". | You have to find "groups" in unlabeled data. |
| Input Data is labeled? | Labeled Data                          | Labeled Data                                     | Unlabeled Data                               |
| Target Variable is?    | Continuous                            | Categorical                                      | No Target                                    |

# K-Nearest Neighbors

**Problem**: We want to classify a new data point $P(7, 6)$ into one of two classes: **Class A** or **Class B** and We have the following dataset:

| Point (x, y) | Class |
| ------------ | ----- |
| (1, 1)       | A     |
| (2, 2)       | A     |
| (3, 3)       | A     |
| (8, 8)       | B     |
| (9, 9)       | B     |
| (10, 10)     | B     |

1. **Choose the value of k**
	Let $k = 3$. This means we’ll look at the **3 nearest neighbors** to classify the new point.

2. **Calculate distances** using Euclidean Distance formula
	Use the **Euclidean Distance** formula to calculate the distance between P(7, 6) and all other points:

$\text{Distance} = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$

| P(x, y)  | Class | Distance to P(7,6)P(7, 6)P(7,6)                     |
| -------- | ----- | --------------------------------------------------- |
| (1, 1)   | A     | $\sqrt{(7-1)^2 + (6-1)^2} = \sqrt{36 + 25} = 7.81$  |
| (2, 2)   | A     | $\sqrt{(7-2)^2 + (6-2)^2} = \sqrt{25 + 16} = 6.40$  |
| (3, 3)   | A     | $\sqrt{(7-3)^2 + (6-3)^2} = \sqrt{16 + 9} = 5.00$   |
| (8, 8)   | B     | $\sqrt{(7-8)^2 + (6-8)^2} = \sqrt{1 + 4} = 2.24$    |
| (9, 9)   | B     | $\sqrt{(7-9)^2 + (6-9)^2} = \sqrt{4 + 9} = 3.61$    |
| (10, 10) | B     | $\sqrt{(7-10)^2 + (6-10)^2} = \sqrt{9 + 16} = 5.00$ |
3. **Identify the k nearest neighbors**
	Sort the points by distance (ascending order) and pick the 3 nearest neighbors:
	In our case, the three nearest points are:
- (8,8) --> 2.24 belongs to Class A
- (9,9) --> 3.61 belongs to Class A
- (3,3) --> 5.00 belongs to Class B

Since, there are 2 nearest for Class A vs 1 nearest for Class B; The majority class is **Class A**. Hence now our point $P(7,6)$ belongs to Class A.



# 1. Data
> Data is the raw, unorganized facts, figures, and symbols. It is the basic building block of information and can exist in various forms, such as numbers, text, images, audio, and video

**Variables** --> characteristics or properties within a dataset that can vary. In a student dataset, variables could include Age, Name, Gender, and Marks.
- *Independent Variables* (Features): Variables that stand alone and can influence other variables. Example: Number of study hours.
- *Dependent Variables* (Target): Variables that depend on other variables. Example: Final exam score (depends on study hours).

## 1.1. Data Types
> They are fundamental categories that define how data should be handled and processed.

> [!note] Why Data Types Matter
> Understanding data types is important because they:
> - Determine how data is stored and processed
> - Affect memory usage and computational efficiency
> - Influence the choice of analysis methods
> - Impact the accuracy of results

***KEY DATA TYPES***
1. **Numerical Data** (Numbers)
	- *Integers* --> Whole numbers (Counting data, Age in years etc.)
	- *Floats* --> Decimal numbers (Measurements, Percentages, Financial data etc.)
2. **Categorical Data** (Categories)
	- *Nominal* --> Categories without order (Colors, Gender, Blood Types etc.)
	- *Ordinal* --> Categories with order (Rank, Satisfaction, Grades etc.)
3. **Text Data** (Text)
	- Used for -> Social media posts, Product descriptions, Email content etc.
4. **Boolean Data** (Binary)
	- Used for -> True/False flags, Status indicators, Condition checks etc.
## 1.2. Structured vs. Unstructured Data

**Structured Data** --> Organized in predefined formats, Follows a schema or data model and it is easy to search and analyze.
- *Examples*: SQL databases, Excel spreadsheets, CSV files, Time series data

**Unstructured Data** --> No predefined structure, Harder to process and analyze and requires specialized tools.
- *Examples*: Text documents, Images and videos, Audio files, Social media content

> [!tip] Working with Different Data Types
> When working with different data types:
> 1. Always validate data types before analysis
> 2. Convert data types when necessary
> 3. Handle missing values appropriately
> 4. Document any data type transformations
## 1.3. Data Collection Methods

**Primary data collection** involves gathering data directly from the source. 
* *Advantages*: The data is tailored to your specific needs. Primary data is generally considered to be more accurate.
* *Disadvantages*: Collecting primary data can be time-consuming. Primary data collection can be expensive.
* *Examples*: surveys, interviews, and observations.

**Secondary data collection** uses data that has already been collected by someone else. 
* *Advantages*: Secondary data is usually cost-effective. Secondary data is readily available. 
* *Disadvantages*: Secondary data may not perfectly fit your needs. The data may be outdated.
* *Examples*: government databases, research papers, and online sources.

> [!note] Choosing Collection Methods
> The choice of data collection method depends on:
> - Research objectives
> - Available resources
> - Time constraints
> - Data quality requirements
## 1.4. Data Quality Characteristics

1. *Accuracy* --> Data correctness, Minimal errors, Verified sources
2. *Completeness* --> No missing values, All required fields present, Comprehensive coverage
3. *Consistency* --> Uniform formats, Standardized values, No contradictions
4. *Timeliness* --> Up-to-date information, Regular updates, Relevant time period
## 1.5. Common Data Issues

> [!warning] Data Quality Issues
> Common problems that need addressing:

1. **Missing Data**
   > [!example] Handling Missing Data
   > - **Detection Methods** --> Null value checks, Empty string checks, Special value checks (e.g., -999)
   > - **Solutions** --> Remove rows (if few missing values), Impute with mean/median, Use advanced imputation methods, Create 'missing' category

2. **Duplicate Data**
   > [!example] Handling Duplicate Data
   > - **Identification** --> Exact matches, Fuzzy matches, Business key matches
   > - **Solutions** --> Remove duplicates, Merge information, Keep most recent, Flag duplicates

3. **Inconsistent Data**
   > [!example] Handling Inconsistent Data
   > - **Common Issues** --> Different date formats, Varying units, Inconsistent spelling
   > - **Solutions** --> Format standardization, Unit conversion, Spelling normalization

## 1.6. Data Transformation Techniques

1. **Normalization** --> A data preprocessing to adjust numerical values to a common scale, typically between 0 and 1. This process prevents variables with large ranges from dominating the analysis and ensures that all features contribute equally to the machine learning model.
	- *Min-Max Scaling* --> Formula: $(x - min)/(max - min)$ | Range: $[0, 1]$
	- *Z-Score Normalization* --> Formula: $(x - mean)/std$ | Range: $(-3, 3)$
	- *Decimal Scaling* --> Formula: $x/10^n$ | Range: varies

2. **Encoding** --> A data preprocessing technique that converts text-based categorical variables into a numerical format that machine learning algorithms can understand.
	- *One-Hot Encoding* --> Binary columns for each category, No ordinal relationship
	- *Label Encoding* --> Single column with integers, Maintains ordinal relationship
	- *Binary Encoding* --> Binary representation, Memory efficient

---

# 2. Exploratory Data Analysis (EDA)

> [!note] Purpose of EDA
> EDA helps:
> - Understand data distribution
> - Identify patterns and relationships
> - Detect anomalies
> - Generate hypotheses

## 2.1. Summary Statistics

1. Measures of **Central Tendency**
	- *Mean*: arithmetic average
	- *Median*: middle value
	- *Mode*: most frequent value
2. Measures of **Spread**
	- *Range*: max value - min value
	- *Variance*: average squared deviation
	- *Standard deviation*: square root of variance
	- *Quartiles*: divide data into four parts
3. Measures of **Shape**
	- *Skewness*: asymmetry measure
	- *Kurtosis*: tail heaviness measure
## 2.2. Visualization Techniques
1. Univariate or Single Variable Plots
	1. **Histograms** --> Show distribution, Identify patterns, Detect outliers
	2. **Box Plots** --> Show quartiles, Identify outliers, Compare groups
	3. **Bar Charts** --> Compare categories, Show frequencies, Display proportions
2. Bivariate or Two Variable Plots
	1. **Scatter Plots** --> Show relationships, Identify correlations, Detect patterns
	2. **Line Plots** --> Show trends, Compare changes, Time series analysis
	3. **Heat Maps** --> Show correlations, Identify patterns, Compare categories

---

# 3. Machine Learning
> Machine learning is a subset of artificial intelligence (AI) that allows systems to learn from data, improving their performance over time without explicit programming.

Machine learning *enables computers* to: Learn from data, Identify patterns, Make predictions and Improve with experience.

> [!TIP] Uses of Machine Learning
> * **Predictive analytics:** Forecasting future trends, such as sales forecasting.
>* **Recommendation systems:** Suggesting products or services based on user preferences, as seen on Netflix and Amazon.
>* **Image and speech recognition:** Identifying faces or understanding spoken language, used in facial recognition software and voice assistants.
>* **Natural language processing:** Enabling computers to understand and process human language, used in chatbots and language translation tools.
## 3.1. Types of Machine Learning
1. **Supervised Learning:** The model is trained on labeled data (which includes input-output pairs) This means the algorithm is given both the input features and the desired output, allowing it to learn the relationship between them.
	- *Types* -> **Classification** and **Regression**
    * *Algorithms* -> Linear Regression, Decision Trees, Support Vector Machines (SVM) etc.
    * *Uses* -> Email Spam Detection, Credit Scoring etc. 
2. **Unsupervised Learning:** The model is trained on unlabeled data, meaning it must discover patterns and groupings on its own without specific output guidance.
	- *Types* -> **Clustering**, **Association** and **Dimensionality Reduction**
    * *Algorithms* -> K-Means Clustering, Principal Component Analysis (PCA), and Hierarchical Clustering.
    * *Uses* -> 	Pattern discovery, Feature extraction etc.
3. **Reinforcement Learning:** This type involves an agent learning to make decisions in an environment to maximize cumulative rewards. The agent interacts with the environment, receives feedback in the form of rewards or penalties, and adjusts its actions accordingly.
    * *Algorithms* -> Q-Learning and Deep Q-Networks (DQN).
    * *Uses* -> Games, Robots, Trading strategies etc.
## 3.2. Machine Learning Workflow
1. *Problem Definition* -> Clearly define the problem you want to solve.
2. *Data Collection* -> Gather relevant data from various sources.
3. *Data Preprocessing* -> Prepare the data for analysis by cleaning, transforming, and handling missing values.
4. *Model Selection* -> Choose an appropriate machine learning algorithm based on the problem type and the nature of the data.
5. *Training the Model* -> Use the prepared data to train the model, allowing it to learn patterns and relationships within the data.
6. *Model Evaluation* -> Evaluate the model's performance using metrics such as accuracy, precision, recall, and F1-score.
7. *Model Deployment* -> Once the model is trained and evaluated, it can be deployed for real-world use, making predictions or decisions based on new data.
## 3.3. Neural Networks
> A specific type of machine learning model inspired by the structure and function of the human brain. They consist of interconnected nodes, or "neurons," organized in layers.

**Neuron Structure** --> Inputs, Weights, Bias, Activation function, Output.

**Layered Structure:**
1. *Input Layer*: Receives the raw data input, similar to how our senses gather information.
2. *Hidden Layers*: Process the information from the input layer, extracting features and patterns through multiple layers of interconnected neurons.
3. *Output Layer*: Provides the final prediction or decision based on the processed information. 

**Learning Process:** 
1. *Weights and Biases*: Each connection between neurons has an associated weight, representing its importance. Biases are additional parameters that help fine-tune the network's learning.
2. *Forward Propagation*: The input data flows through the network, with each layer processing and transforming the information until it reaches the output layer, producing a prediction.
3. *Backpropagation*: The network compares its prediction to the actual output and adjusts the weights and biases based on the error, improving its accuracy over time. 