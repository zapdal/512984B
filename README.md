# Image Classification API with TensorFlow and FastAPI

This project provides an API for image classification using a TensorFlow Lite model. The application is built using FastAPI for the backend and uses TensorFlow/Keras for image processing and prediction.

---

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Setup](#setup)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Example Request](#example-request)
- [Acknowledgements](#acknowledgements)

---

## Overview

The project consists of two main components:
1. **`BACKEND.py`**: Contains the image prediction logic using a TensorFlow Lite model.
2. **`main.py`**: Implements the FastAPI endpoints to interact with the prediction logic.

The model predicts the type of flower from an image URL and classifies it into one of the following categories:
- Daisy
- Dandelion
- Rose
- Sunflower
- Tulip

---

## Features

- **Image Classification**: Classifies an input image (provided via URL) into one of the predefined categories.
- **Confidence Score**: Provides a confidence score for the classification.
- **CORS Support**: Allows cross-origin requests for seamless integration with frontend applications.
- **Error Handling**: Graceful handling of errors with appropriate messages.

---

## Project Structure
. ├── BACKEND.py # Contains the IMG_PRED class for image prediction ├── main.py # FastAPI application defining routes and endpoints ├── model.tflite # TensorFlow Lite model used for predictions └── README.md # Project documentation


---

## Dependencies

The project requires the following dependencies:

- Python 3.7 or later
- TensorFlow
- Keras
- FastAPI
- Uvicorn (for running the FastAPI server)

Install the required dependencies using pip:

```bash
pip install tensorflow keras fastapi uvicorn
Setup
Clone the repository:
git clone <repository-url>
cd <repository-directory>
Ensure that the TensorFlow Lite model file (model.tflite) is present in the project directory.
Install the dependencies:
pip install tensorflow keras fastapi uvicorn
Run the FastAPI server:
uvicorn main:app --reload
The server will start and be accessible at http://127.0.0.1:8000.
Usage
Steps to Use the API:
Ensure the server is running (uvicorn main:app --reload).
Use an HTTP client (e.g., Postman, cURL, or a frontend application) to send requests to the API.
API Endpoints
Root Endpoint
Endpoint: /
Method: POST
Description: Returns a message confirming the purpose of the project.
Response:
"This Project is made for checking tensorflow operation"
Predict Endpoint
Endpoint: /predict/
Method: GET
Description: Performs image classification on an image provided via URL.
Query Parameter:
URL (string): Public URL of the image to be classified.
Response:
On Success:
"This image most likely belongs to <LABEL> with a <CONFIDENCE>% confidence."
On Failure:
"OPERATION FAILED FOR <ERROR_MESSAGE>"
Example Request
To classify an image, send a GET request to the /predict/ endpoint with the URL query parameter.

Using cURL:
curl -X GET "http://127.0.0.1:8000/predict/?URL=https://example.com/image.jpg"
Using Python (requests library):
import requests

url = "http://127.0.0.1:8000/predict/"
params = {"URL": "https://example.com/image.jpg"}
response = requests.get(url, params=params)
print(response.json())
Acknowledgements
TensorFlow for providing a robust machine learning framework.
FastAPI for creating a high-performance API.
Uvicorn for running the ASGI server.
Notes
Ensure the model.tflite file is present in the project directory.
The input image should be publicly accessible via the provided URL.
The model expects images resized to 180x180 pixels.
Happy coding! 🎉


This `README.md` file provides an overview, setup instructions, usage details, and API documentation for your project. Let me know if you need further customization!