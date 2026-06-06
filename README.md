# AI-Based Emotion Detection Web Application

A Flask-based web application that detects emotions from text using IBM Watson NLP. Built as a final project for the IBM AI Application Development course.

---

## Project Overview

This application accepts a text input from the user and returns the detected emotion scores — anger, disgust, fear, joy, and sadness — along with the dominant emotion. It is powered by IBM Watson's Emotion Prediction NLP model and deployed via a Flask web server.

---

## Project Structure

```
oaqjp-final-project-emb-ai/
├── EmotionDetection/
│   ├── __init__.py               # Package initializer
│   └── emotion_detection.py      # Core emotion detection function
├── static/
│   └── mywebscript.js            # Frontend JavaScript
├── templates/
│   └── index.html                # Frontend HTML page
├── server.py                     # Flask web server
├── test_emotion_detection.py     # Unit tests
└── README.md                     # Project documentation
```

---

## Features

- Detects 5 emotions: anger, disgust, fear, joy, and sadness
- Identifies the dominant emotion from any text input
- Handles blank/invalid input gracefully with error messages
- Clean web interface built with Bootstrap
- Fully tested with unit tests for all 5 emotions
- Passes pylint static code analysis with a score of 10/10

---

## Technologies Used

- Python 3.10
- Flask
- IBM Watson NLP (Emotion Prediction Model)
- HTML / CSS / Bootstrap
- JavaScript (XMLHttpRequest)
- unittest (Python standard library)
- pylint

---

## Setup and Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/oaqjp-final-project-emb-ai.git
cd oaqjp-final-project-emb-ai
```

### 2. Install dependencies

```bash
python3.10 -m pip install requests flask
```

### 3. Run the application

```bash
python3 server.py
```

### 4. Open in browser

Navigate to:
```
http://localhost:5000
```

---

## Usage

1. Enter any text in the input field on the web page
2. Click **"Run Sentiment Analysis"**
3. The application will display the emotion scores and the dominant emotion

Example output:
```
For the given statement, the system response is 'anger': 0.004081481,
'disgust': 0.0005366061, 'fear': 0.0067288913, 'joy': 0.9937042 and
'sadness': 0.01218069. The dominant emotion is joy.
```

---

## Running Unit Tests

```bash
python3 -m unittest test_emotion_detection.py -v
```

Expected output:
```
test_anger_for_angry_text ... ok
test_disgust_for_disgusting_text ... ok
test_fear_for_fearful_text ... ok
test_joy_for_happy_text ... ok
test_sadness_for_sad_text ... ok

Ran 5 tests in 0.615s
OK
```

---

## Running Static Code Analysis

```bash
pylint server.py
```

Expected score: **10.00/10**

---

## Error Handling

If a blank or invalid input is submitted, the application returns:
```
Invalid text! Please try again.
```

This is handled by checking for a 400 status code from the Watson API.

---

## API Details

- **Endpoint:** `https://sn-watson-emotion.labs.skills.network/v1/watson.runtime.nlp.v1/NlpService/EmotionPredict`
- **Model:** `emotion_aggregated-workflow_lang_en_stock`
- **Method:** POST
- **Note:** This API is only accessible from within the IBM Skills Network lab environment

---

## License

This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.
