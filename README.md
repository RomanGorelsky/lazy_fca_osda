BigHW project for OSDA course

# Lazy FCA (Formal Concept Analysis) Classifcation.

This README file contains the description of the final project in the course **Ordered Sets for Data Analysis**.

In general, we are solving the task of binary classification. It means that there are only two possible values for the target class (usually denoted as + and -).

As an input we are given a train set in which the class labels for the object is known, and a test dataset in which the objects and their features are given but without the class label.

  

We will follow the lazy learning approach in the classification task, which means that the step for building the classification is eliminated, and as soon as we get test object (query object) we need to assign a class label to it, using existing data from the train set.

  

The project consists of the following steps:

1. Choose a binary dataset. You can use open dataset cites like [UCI](https://archive.ics.uci.edu/datasets) and [Kaggle](https://www.kaggle.com/datasets).

2. Perform exploratory data analysis on the dataset to analyze and investigate the chosen dataset and to summarize its main characteristics. Based on this step, irrelevant columns and rows can be dropped, missing values for the features can be filled, and a general understanding about how the class is related to the features can be formed.

3. Choose the direction of work: binarize  the features (data scaling) or use Pattern Structures. The original FCA lazy classification algorithm expects only binary features and there are specific methods to binarize different types of data to make them suitable for FCA algorithms. These methods are called data scaling methods. Another option is to choose not to binarize data and instead use a generalization of FCA that allows for complex data descriptions such as Pattern Structures.

4. Apply the chosen direction on the test set form the dataset and calculate the following quality metrics:

- True Positive.

- True Negative.

- False Positive.

- False Negative.

- True Negative Rate (Specificity).

- Negative Predictive Value.

- False Positive Rate.

- False Discovery Rate.

- Accuracy.

- Precision.

- Recall (True Positive Rate).

- F1 Score.

  

5. Compare the achieved performance with other standard classification algorithms like:

- K Nearest Neighbor (kNN).

- Naive Bayes.

- Logistic Regression.

- SVM.

- Decision Tree.

- Random Forest.

- XGBoost.


6. Improve the performance of the algorithm. Any modification is allowed (the way of identifying positive/negative classifiers, the definition of positive/negative classifiers, the aggregation of classifiers, etc.).

7. Provide an analysis of interpretability. You need to show how interpretable your model is in comparison with other models. Any way of increasing interpretability is a plus.

8. Organize a report in which you describe the dataset you chose and the steps you perfomed alongside the values of the quality metrics and the results of the comparison. Do not forget the interpretability analysis.

9. Upload the report and the code to a google form (the link will be given in the future).

  
  

## A small introduction to the one FCA lazy classification approach called the "Generators" method:

  

Split the train set of the dataset into two contexts: $C_+$ that contains all positive examples and $C_-$ that contains all negative examples. To classify a test example (query example) we follow this procedure:

  

1. for each positive object $g_+ \in C_+$ we calculate the intersection between the description of this positive object $(g_+')$ and the description of the test object $(g')$. We then check whether this description (intersection) is presented in any example from $C_-$.

  

2. for each negative object $g_- \in C_-$ we calculate the intersection between the description of this negative object $(g_-')$ and the description of the test object $(g')$. We then check whether this description (intersection) is presented in any example from $C_+$.

  

You have to explore several aggrgation functions to perform the classifcation. One possible example is:

  

- You classify the test object as +, if for the interections with examples from $C_+$ you have no more that $x$ counter-examples, and for the intersections with no counter-examples the size of the intersection (cardinality) is at least min_cardinality.



## Grading system (out of 10):

1. Performing steps 1-6 will grants a maximum of 3/10.

2. Improving on the algorithm grants a maximum of 2/10.

3. Intepretability analysis grants a maximum of 2/10.

4. Presenting the work grants a maximum of 3/10.


p.s. Not uploading the report before the deadline will result in a 0 mark.
 
## Examples:
- An example of FCA-based lazy classification using scaling is provided in: [lazy_fca.ipynb](lazy_fca.ipynb).

- An example of FCA-based lazy classification using interval pattern structures is provided in: [lazy_fca_ips.ipynb](lazy_fca_ips.ipynb).

