# 📚 LDA Topic Modeler with Flask API

This repository contains a Flask app that automates the process of _**topic modeling**_ using Latent Dirichlet Allocation (LDA) on a given dataset of open-ended answers. The app provides endpoints to process data, train the LDA model, generate topic names using OpenAI, and predict the topic of a given text. The solution aims to be simple, scalable, and robust.

The main objective is to help the Project Support team automate one of their time-consuming manual tasks of classifying open-ended answers among candidate topics.

## Features

- Preprocessing and cleaning of input text data from Yahoo Answers dataset
- Training an LDA model for topic modeling
- Generating human-readable topic names using OpenAI
- Flask REST API for processing, training, naming, and topic prediction
- Error handling to account for unexpected situations

## 🚀 Getting Started

To run the app locally, follow these steps:

1. Clone this repository:

```bash
git clone -b master https://github.com/Josh-Em/potloc-topic-modeler.git
cd potloc-topic-modeler
```

2. Set up a virtual environment and activate it:

For Windows:
```
python -m venv env
env\Scripts\activate
```

For macOS/Linux:
```
python3 -m venv env
source env/bin/activate
```

3. Install the required dependencies:

```
pip install -r requirements.txt
```

4. Set up OpenAI API key:

Change the following line in the **app.py file** with your OpenAI API key:

```bash
api_key = "you_api_key_here"
```

5. Run the Flask app:

```bash
flask run
```

6. Open your web browser and navigate to `http://127.0.0.1:5000`.
   
## API Endpoints

This Flask app provides the following REST API endpoints:

- `/process_data`: Accepts the **technical-test-dataset.csv file** containing the Yahoo Answers dataset and processes it (POST)
- `/train_model`: Trains the LDA model using the processed dataset (POST)
- `/name_topics`: Accepts an array of generated topics and returns topic names using OpenAI (POST)
- `/predict_topic`: Accepts a text string and predicts the most probable topic using the trained LDA model (POST)

## 🔨 Next Steps & Improvements

1. Improve text preprocessing and filtering by incorporating more NLP libraries and techniques (e.g., NER, dependency parsing, etc.).
2. Evaluate and compare other topic modeling algorithms (e.g., Top2Vec, BERTopic) to potentially improve topic quality and relevance.
3. Introduce hyperparameter tuning to optimize the performance of the LDA model.
4. Enhance topic naming by combining multiple OpenAI outputs or using other sources for topic name generation.
5. Provide an interactive user interface for the Flask app to ease user interaction and visualization of topics.
6. Implement a secured and production-ready API design, considering authentication, rate limiting, and deployment options.
7. Track and monitor model performance over time, introducing online training and automatic model updating to adapt to evolving topics.
