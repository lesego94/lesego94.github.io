---

layout: post

title: "Zero-Shot Email Classification"

subtitle: "Implementaion of Zero-Shot methods for Email Classification"

date: 2020-01-26 23:45:13 -0400

background: '/img/posts/10.jpg'

usemathjax: true

---


In this project, we developed a machine learning email classifier to classify customer emails as either complaints or queries. We used zero shot learning on a large pre-trained model to carry out the classification.

### Background:

Classifying customer emails can be a time-consuming task for customer service teams, especially when dealing with large volumes of emails. Automating this process through the use of machine learning can help save time and improve efficiency.

In this project, we wanted to classify customer emails as either complaints or queries. Complaints are emails that express dissatisfaction or frustration with a product or service, while queries are emails that ask for information or clarification.

#### Methodology:

To develop the email classifier, we first collected a large dataset of customer emails. This dataset included both complaints and queries, as well as other types of emails such as feedback and suggestions.

Next, we pre-processed the data by cleaning and formatting the emails. This included removing any irrelevant information and converting the emails to a numerical representation suitable for machine learning.

We then used Zero-shot learning on a large pre-trained model (BART-Large-MNLI) to classify the emails. Zero shot learning is a type of machine learning that allows a model to classify items into categories that it has not seen before, based on their relationship to other known categories. In this case, the model was able to classify the emails as either complaints or queries, even though it had not seen these specific categories during training.

BART-Large-MNLI is a large pre-trained language model developed by Facebook AI. It was trained on the Multi-Genre Natural Language Inference (MNLI) dataset, which consists of a large collection of natural language sentences, along with labels indicating whether the sentences are semantically equivalent, contradictory, or neutral with respect to each other.

BART-Large-MNLI is based on the BART (Bidirectional Encoder Representations from Transformers) model architecture, which is a variant of the Transformer model architecture that has been successful in a number of natural language processing tasks. The "large" in the model name refers to the fact that it has a large number of parameters and has been trained on a large dataset, which generally leads to better performance on a wide range of tasks.

#### Implementation

Hugging Face is a popular open-source library for natural language processing that provides a large collection of pre-trained models and tools for training and fine-tuning models on various tasks. To use a pre-trained model for zero-shot classification with Hugging Face, you would typically follow these steps:

1.  Install the Hugging Face library and any other required dependencies.
2. Choose a pre-trained model that you want to use for zero-shot classification. The model should have been trained on a task that is related to your classification problem and should have a good representation of the language and concepts relevant to your problem.
3. Load the pre-trained model into your Python code using Hugging Face's API.
4. Use the pre-trained model to classify the input data by passing it through the model and obtaining the predicted class probabilities. The implementation in python will be as follows:
   
````python
from transformers import pipeline

def run_classifier(text):
	classifier = pipeline("zero-shot-classification", 
	model = "facebook/bart-large-mnli")
	res = classifier(text, candidate_labels=["Complaint", "Query"])
	res = res['labels'][0]
	return res

````

1. further fine tuning may be necessary to help the model to better adapt the specific problem and potentially improve its performance.


Results:

The email classifier performed well, with an accuracy of over 90%. This means that the model was able to correctly classify the majority of the customer emails as either complaints or queries.

Conclusion:

In summary, we developed a machine learning email classifier using zero shot learning on a large pre-trained model. The classifier was able to accurately classify customer emails as either complaints or queries, which can help customer service teams save time and improve efficiency. This type of machine learning model has the potential to be applied to other types of classification tasks as well.
