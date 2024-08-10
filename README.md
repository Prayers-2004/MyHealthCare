# Sentiment Analysis API

This is a simple Flask API for sentiment analysis using the `transformers` library and a pre-trained BERT model.

## Installation

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2. Create a virtual environment and activate it:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Run the Flask application:
    ```bash
    python app.py
    ```

2. Send a POST request to the `/predict` endpoint with a JSON payload containing the text to analyze:
    ```bash
    curl -X POST http://127.0.0.1:5000/predict -H "Content-Type: application/json" -d '{"text": "I love this!"}'
    ```

## Example

Here is an example of how to use the API:

```python
import requests

url = "http://127.0.0.1:5000/predict"
data = {"text": "I love this!"}
response = requests.post(url, json=data)
print(response.json())

Endpoints
POST /predict: Analyzes the sentiment of the provided text.
Request body: JSON object with a text key.
Response: JSON object with the sentiment analysis result.
Error Handling
If the text key is missing in the request body, the API will return a 400 status code with an error message.
If any other error occurs, the API will return a 400 status code with the error message.
Dependencies
Flask
Flask-CORS
transformers
License
This project is licensed under the MIT License.