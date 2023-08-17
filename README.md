# creditcard_fraud_detection

By creating a reliable anomaly detection system, this project intends to solve the growing problem of credit card theft. The study concentrates on spotting unexpected trends in credit card transactions by utilizing cutting-edge deep learning techniques. An efficient anomaly detection model is trained using an extensive dataset of both legitimate and fraudulent transactions. In order to provide precise fraud detection while reducing false positives, the final system is assessed using precision, recall, and F1-score criteria. This initiative has the potential to greatly improve fraud detection skills and contribute to a more secure financial sector.

## DATASET:
The dataset was gathered and examined as part of a research cooperation on big data mining and fraud detection between Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) at ULB (Université Libre de Bruxelles). On the DefeatFraud project website and further information on ongoing and completed initiatives on relevant subjects is accessible.
The dataset includes credit card transactions performed by European cardholders in September 2013. We have 492 frauds out of 284,807 transactions in our dataset of transactions that took place over the course of two days. The dataset is quite skewed, with frauds making up 0.172% of all transactions in the positive class. It only has numeric input variables that have undergone PCA transformation. Unfortunately, we are unable to offer the original characteristics and further context for the data due to confidentiality concerns. The major components derived with PCA are features V1, V2, …, V28; the only features that have not been changed with PCA are "Time" and "Amount". The seconds that passed between each transaction and the dataset's initial transaction are listed in the 'Time' feature. The transaction amount is represented by the feature "Amount," which may be utilised for example-dependent, cost-sensitive learning. The response variable, feature "Class," has a value of 1 in cases of fraud and 0 in all other cases. We suggest testing accuracy using the Area Under the Precision-Recall Curve (AUPRC) in light of the class imbalance ratio. For categorization that is not balanced, confusion matrix accuracy is meaningless.

Implementing the Deep Learning Algorithm
A sophisticated anomaly detection system is built in the second phase using cutting-edge deep learning methods. Several strategies can be used, such as data preparation, model architecture, training and evaluation.
1.	Fully Connected Neural Network (FCN):
A traditional design utilised for a variety of applications, such as tabular data processing like credit card fraud detection, is the fully connected network (also known as a feedforward neural network). There are several hidden layers, an input layer, and an output layer. Each neuron in a layer is linked to every other neuron in the layer below. Standardise your dataset's features, encode categorical variables, and divide it into training and test sets as part of the preprocessing phase. Utilise tools such as TensorFlow or PyTorch to create a fully connected neural network. Specify the number of neurons in each layer, the activation mechanisms, and the regularisation strategies. Using the training data, train the model, and track accuracy and loss. Utilise the test set to evaluate the model. Calculate the F1-score, recall, accuracy, precision, and recall for fraud detection.

2.	Recurrent Neural Network (RNN):
RNNs work well with sequences like time series data. They have connections that loop back, which enables them to keep track of earlier inputs like records with the same featured value. You may capture temporal interdependence in your situation by using historical records as a time sequence. Create a time-based dimension and convert your tabular data into a sequential format. Use TensorFlow or PyTorch libraries to build an RNN architecture, such as the Long Short-Term Memory (LSTM) model. Set the units, layers, and dropout parameters.  Utilise the sequential data to train the RNN. To build input sequences, think about employing strategies like windowing. Use test data to assess the model in a manner similar to FCN. Pay close attention to prediction sequences for abnormalities due to the temporal aspect.

3.	TabNet:
A specific architecture for tabular data is called TabNet. It combines elements of neural networks and decision trees and focuses on gleaning useful information from high-dimensional, noisy input.  Preprocess your dataset in a manner akin to FCN. Both category and numerical features perform well with TabNet. Set up the pytorch_tabnet library's TabNetClassifier. Utilise the training data to train the TabNet model. TabNet selects characteristics automatically, concentrating on those that are important for prediction. Utilise test data to evaluate the model. Keep track of precision and other important parameters.

## RESULTS
High accuracy (0.98) and balanced precision (0.99) and recall (0.97) were attained using FCN. It did a remarkable job of detecting fraud situations and reducing false positives. This makes it appropriate for situations when accuracy and memory are equally crucial. Strengths of FCN high precision, able to classify fraud with accuracy. Consider addressing class imbalance, tweaking hidden layers, and researching other activation functions as ways to get better.
The accuracy, precision, and recall of TabNet were remarkably high (0.99). TabNet achieved a high F-score (0.99) by expertly balancing recall and accuracy. Its stability across all criteria makes it the best option. Outstanding recall, accuracy, and F-score are among TabNet's best traits. To improve, explore with feature engineering and hyperparameters for even better feature selection.
 
RNN presented a strong performance with a 0.93 accuracy, 0.9889 high precision, and 0.93 balanced F-score. Recall was somewhat lower (0.88) although it did identify a sizable percentage of fraud instances. When temporal patterns are important, RNN performs well. Strengths of RNN F-score with strong accuracy and balance. Try out various topologies (LSTM, GRU) and data augmentation strategies to better capture temporal patterns in order to improve recall. [11]
Model selection: TabNet is the clear winner thanks to its outstanding performance across all criteria. It offers a strong solution for fraud detection by striking a balance between recall and accuracy.
