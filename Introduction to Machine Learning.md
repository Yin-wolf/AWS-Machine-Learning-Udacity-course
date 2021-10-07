
# Introduction to Machine Learning

## What is Machine Learning?

A modern software development technique that allows computers to automatically learn and improve from experience without being explicitly programmed to do so.
In Machine Learning are several different kinds of techniques:

- In  **supervised learning**, every training sample from the dataset
   has a corresponding label or output value associated with it. As a
   result, the algorithm learns to predict labels or output values.

- In  **reinforcement learning**, the algorithm figures out which
   actions to take in a situation to maximize a reward (in the form of a number) on the way to reaching a specific goal.

- In  **unsupervised learning**, there are no labels for the training
   data. A machine learning algorithm tries to learn the underlying
   patterns or distributions that govern the data.

## Components of Machine Learning

There are 3 components in Machine Learning.

### 1. Machine Learning Model

A framework that can be modified to solve different but related problems based on the data provided.
> A model is an extremely generic program(or block of code), made specific by the data used to train it. It is used to solve different problems.

#### Example: Selling of Snow Cones w.r.t Temp

### 2. Model Training Algorithm

Basic step in training a model:

 1. Think about the changes that need to be made (Inspect and Evaluate)
 2. Make those changes
 3. Repeat

### 3. Model Inference Algorithm

Using the trained model to generate predictions.

## Introduction to the Five Machine Learning Steps

### Step 1: Define the Problem

---

#### Machine Learning Tasks

|                |Supervised Learning                          |Unsupervised Learning                     |
|----------------|-------------------------------|-----------------------------|
|Type| Labeled Data            | Unlabeled Data            |
|Meaning          |Data for which you already know the target answer            |Data that can be used for training but does not contain labels            |
|Types |Categorical Label (Classification), Continuous Label (Regression), etc |Clustering, etc|

> A  **categorical** label _has a_ discrete _set of possible values. In a machine learning problem in which you want to identify the type of flower based on a picture, you would train your model using images that have been labeled with the categories of flower you would want to identify._

> A  **continuous** (regression) label _does not have a discrete set of possible values, which often means you are working with numerical data._

> **Clustering** is Unsupervised learning task that helps to determine if there are any naturally occurring groupings in the data.
---

### Additional Reading

- The  [AWS Machine Learning blog](https://aws.amazon.com/blogs/machine-learning/)  is a great resource for learning more about projects in machine learning.
- You can use Amazon SageMaker  [to calculate new stats in Major League Baseball](https://aws.amazon.com/blogs/machine-learning/calculating-new-stats-in-major-league-baseball-with-amazon-sagemaker/).
- You can also find an article on  [Flagging suspicious healthcare claims with Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/flagging-suspicious-healthcare-claims-with-amazon-sagemaker/)  on the AWS Machine Learning blog.
- What [kinds of questions and problems](https://docs.aws.amazon.com/machine-learning/latest/dg/machine-learning-problems-in-amazon-machine-learning.html)  are good for machine learning?

---

### Step 2: Build a Dataset

---

#### The most important step of the machine learning process

Working with data is perhaps the most overlooked—yet most important—step of the machine learning process. In 2017, an O’Reilly study showed that machine learning practitioners spend **80%** of their time working with their data.

#### *The Four Aspects of Working with Data*

    Data Collection <---> Data Inspection <---> Summary Statistics <---> Data Visualization

#### 1. Data collection

Find and Collect the data related to the problem

> Does the data you've collected match the machine learning task and problem you have defined?

#### 2. Data inspection

The quality of your data will ultimately be the largest factor that affects how well you can expect your model to perform. As you inspect your data, look for:

- Outliers
- Missing or incomplete values
- Data that needs to be transformed or preprocessed so it's in the correct format to be used by your model

#### 3. Summary statistics

Models can assume how your data is structured.

Now that you have some data in hand it is a good best practice to check that your data is in line with the underlying assumptions of your chosen machine learning model.

With many statistical tools, you can calculate things like the mean, inner-quartile range (IQR), and standard deviation. These tools can give you insight into the  _scope_,  _scale_, and  _shape_ of the dataset.

#### 4. Data visualization

You can use data visualization to see outliers and trends in your data and to help stakeholders understand your data.

---

### Additional reading

- In machine learning, you use several statistical-based tools to better understand your data. The  `sklearn`  library has many examples and tutorials, such as this example demonstrating  [outlier detection on a real dataset](https://sklearn.org/auto_examples/applications/plot_outlier_detection_housing.html#sphx-glr-auto-examples-applications-plot-outlier-detection-housing-py).

---

### Step 3: Model Training

#### Splitting your Dataset

The first step in model training is to randomly split the dataset. This allows you to keep some data hidden during training, so that data can be used to evaluate your model before you put it into production. Specifically, you do this to test against the bias-variance trade-off.
Splitting your dataset gives you two sets of data:

- _Training dataset_: The data on which the model will be trained. Most of your data will be here. Many developers estimate about 80%.
- _Test dataset_: The data withheld from the model during training, which is used to test how well your model will generalize to new data.

#### Model Training Terminology

> The model training algorithm iteratively updates a model's parameters to minimize some loss function.

Let's define those two terms:

- _Model parameters_: Model parameters are settings or configurations the training algorithm can update to change how the model behaves.
- _Loss function:_ A loss function is used to codify the model’s distance from this goal.

#### Putting it All Together

The end-to-end training process is

- Feed the training data into the model.
- Compute the loss function on the results.
- Update the model parameters in a direction that reduces loss.

#### Advice From the Experts

Remember the following advice when training your model.

1. Practitioners often use machine learning frameworks that already have working implementations of models and model training algorithms. You could implement these from scratch, but you probably won't need to do so unless you’re developing new models or algorithms.
2. Practitioners use a process called  _model selection_  to determine which model or models to use. The list of established models is constantly growing, and even seasoned machine learning practitioners may try many different types of models while solving a problem with machine learning.
3. _Hyperparameters_  are settings on the model which are not changed during training but can affect how quickly or how reliably the model trains, such as the number of clusters the model should identify.
4. Be prepared to iterate.

> _Pragmatic problem solving with machine learning is rarely an exact science, and you might have assumptions about your data or problem
 which turn out to be false. Don’t get discouraged. Instead, foster a
habit of trying new things, measuring success, and comparing results
across iterations._
---

## Extended Learning

This information provided for the advanced reader.

### Linear models

One of the most common models covered in introductory coursework, linear models simply describe the relationship between a set of input numbers and a set of output numbers through a linear function (think of  _y = mx + b_  or a line on a  _x_ vs y  chart).

Classification tasks often use a strongly related logistic model, which adds an additional transformation mapping the output of the linear function to the range [0, 1], interpreted as “probability of being in the target class.” Linear models are fast to train and give you a great baseline against which to compare more complex models. A lot of media buzz is given to more complex models, but for most new problems, consider starting with a simple model.

### Tree-based models

Tree-based models are probably the second most common model type covered in introductory coursework. They learn to categorize or regress by building an extremely large structure of nested  _if/else blocks_, splitting the world into different regions at each if/else block. Training determines exactly where these splits happen and what value is assigned at each leaf region.

For example, if you’re trying to determine if a light sensor is in sunlight or shadow, you might train tree of depth 1 with the final learned configuration being something like  _if (sensor_value > 0.698), then return 1; else return 0_;. The tree-based model XGBoost is commonly used as an off-the-shelf implementation for this kind of model and includes enhancements beyond what is discussed here. Try tree-based models to quickly get a baseline before moving on to more complex models.

### Deep learning models

Extremely popular and powerful, deep learning is a modern approach based around a conceptual model of how the human brain functions. The model (also called a  _neural network_) is composed of collections of  _neurons_  (very simple computational units) connected together by  _weights_  (mathematical representations of how much information to allow to flow from one neuron to the next). The process of training involves finding values for each weight.

Various neural network structures have been determined for modeling different kinds of problems or processing different kinds of data.

A short (but not complete!) list of noteworthy examples includes:

- **FFNN**: The most straightforward way of structuring a neural network, the Feed Forward Neural Network (FFNN) structures neurons in a series of layers, with each neuron in a layer containing weights to all neurons in the previous layer.
- **CNN**: Convolutional Neural Networks (CNN) represent nested filters over grid-organized data. They are by far the most commonly used type of model when processing images.
- **RNN**/**LSTM**: Recurrent Neural Networks (RNN) and the related Long Short-Term Memory (LSTM) model types are structured to effectively represent  _for loops_  in traditional computing, collecting state while iterating over some object. They can be used for processing sequences of data.
- **Transformer**: A more modern replacement for RNN/LSTMs, the transformer architecture enables training over larger datasets involving sequences of data.

### Machine Learning Using Python Libraries

- For more classical models (linear, tree-based) as well as a set of common ML-related tools, take a look at  `scikit-learn`. The web documentation for this library is also organized for those getting familiar with space and can be a great place to get familiar with some extremely useful tools and techniques.
- For deep learning,  `mxnet`,  `tensorflow`, and`pytorch`  are the three most common libraries. For the purposes of the majority of machine learning needs, each of these is feature-paired and equivalent.

---

### Additional reading

- The Wikipedia entry on the  [bias-variance](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) trade-off can help you understand more about this common machine learning concept.
- In this  [AWS Machine Learning blog post](https://aws.amazon.com/blogs/machine-learning/build-a-model-to-predict-the-impact-of-weather-on-urban-air-quality-using-amazon-sagemaker/), you can see how to train a machine-learning algorithm to predict the impact of weather on air quality using Amazon SageMaker.

---

### Step 4: Model Evaluation

We use various metrics that are tailored to use case of model:

- Precision
- Log Loss
- F1 Score
- Mean Absolute Error
and many more.

#### Remember: This Process is Iterative

Every step we have gone through is highly iterative and can be changed or re-scoped during the course of a project. At each step, you might find that you need to go back and reevaluate some assumptions you had in previous steps.

### Additional reading

The tools used for model evaluation are often tailored to a specific use case, so it's difficult to generalize rules for choosing them. The following articles provide use cases and examples of specific metrics in use.

1.  [This healthcare-based example](https://aws.amazon.com/blogs/machine-learning/create-a-model-for-predicting-orthopedic-pathology-using-amazon-sagemaker/), which automates the prediction of spinal pathology conditions, demonstrates how important it is to avoid false positive and false negative predictions using the tree-based  `xgboost`  model.
2.  The popular  [open-source library  `sklearn`](https://scikit-learn.org/stable/modules/model_evaluation.html)  provides information about common metrics and how to use them.
3.  [This entry from the AWS Machine Learning blog](https://aws.amazon.com/blogs/machine-learning/making-accurate-energy-consumption-predictions-with-amazon-forecast/)  demonstrates the importance of choosing the correct model evaluation metrics for making accurate energy consumption estimates using Amazon Forecast.

### Step Five: Model Inference

- Using the model to solve real problems
- Monitor the results to make sure your model is producing the kinds of results that you expect. There may be times where you reinvestigate the data, modify some of the parameters in your model training algorithm, or even change the model type used for training.
- Model inference involves: Generating Predictions, Finding Patterns in Data, Using a trained model, Testing your model on data its has not seen.

---

Congratulations! You're ready to deploy your model.

---

> Written with [StackEdit](https://stackedit.io/).
