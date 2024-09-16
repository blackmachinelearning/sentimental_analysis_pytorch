# Sentiment Analysis API

This project involves creating a Sentiment Analysis API using Natural Language Processing (NLP). The API takes a piece of text as input and returns the sentiment score of the text. It includes steps for data collection, model training, API creation, and deployment.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Dockerization](#dockerization)
- [Deployment](#deployment)
- [Resources](#resources)
- [License](#license)

## Project Overview
The main objective of this project is to build a sentiment analysis model using a dataset like IMDB movie reviews or Amazon product reviews. The model can then be accessed through a REST API built with FastAPI. The API is containerized using Docker and can be deployed to platforms such as Heroku, Google Cloud Run, or AWS Lambda.

## Technologies Used
- **Programming Language**: Python
- **Machine Learning Libraries**: Scikit-learn, Hugging Face Transformers (optional for BERT)
- **Web Framework**: FastAPI
- **Containerization**: Docker
- **Deployment**: (Optional) Heroku, Google Cloud Run, AWS Lambda

## Setup Instructions

### Prerequisites
- Python 3.8 or higher
- Docker (for containerization)
- Git (optional, for cloning the repository)

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/sentiment-analysis-api.git
cd sentiment-analysis-api
```

### Step 2: Install Dependencies
Create a virtual environment and install the required packages:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```
### Step 3: Data Collection and Preprocessing
- Download the dataset (IMDB Movie Reviews or Amazon Product Reviews) from Kaggle.
- Preprocess the data by cleaning the text (removing stop words, punctuation, etc.).

### Step 4: Model Training
- Train a Naive Bayes model using Scikit-learn or a BERT model using Hugging Face Transformers.
- Save the trained model for later use in the API.

### Step 5: Running the API Locally
Start the FastAPI server:

```bash
Copy code
uvicorn main:app --reload
```
The API will be available at http://127.0.0.1:8000.

## Usage
- Use the /predict endpoint to send a POST request with a piece of text and receive a sentiment score.
- Example request:
```bash
Copy code
curl -X 'POST' \
  'http://127.0.0.1:8000/predict' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "text": "I love this movie!"
}'
```
## Dockerization
### Step 1: Build the Docker Image
Create a Dockerfile and build the Docker image:

```bash
docker build -t sentiment-analysis-api .
```
### Step 2: Run the Docker Container
```bash
docker run -p 8000:8000 sentiment-analysis-api
```
The API will be available at http://localhost:8000.

## Deployment (Optional)
- Deploy the Dockerized application to Heroku, Google Cloud Run, or AWS Lambda.
- Follow the platform-specific instructions for deploying a Docker container.
## Resources
- **IMDB Dataset:** Kaggle IMDB Movie Reviews
- **FastAPI Tutorial:** FastAPI Documentation
- **Docker Tutorial:** Dockerizing a Python Application
