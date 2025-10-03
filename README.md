# VerbaTwin: Semantic Similarity API

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

VerbaTwin is a deployable NLP service designed to calculate the semantic similarity between two pieces of text. It is built with a modern Python stack and fully containerized with Docker for seamless setup and deployment.

## ✨ Key Features

-   **Semantic Similarity Scoring**: Leverages spaCy's powerful word vectors to determine how closely related two texts are in meaning.
-   **RESTful API**: Exposes a clean and simple API endpoint for easy integration into other applications.
-   **Dockerized Environment**: Uses Docker and Docker Compose to containerize the entire stack (Flask API, spaCy model, MongoDB) for one-command setup.
-   **User Management**: Includes basic endpoints for user registration and API token management, backed by a MongoDB database.

## 🛠️ Tech Stack

-   **Backend**: Python, Flask, spaCy
-   **Database**: MongoDB
-   **Deployment**: Docker, Docker Compose

## 🚀 Getting Started

Follow these instructions to get the project running on your local machine.

### Prerequisites

-   [Git](https://git-scm.com/)
-   [Docker](https://www.docker.com/products/docker-desktop/) and [Docker Compose](https://docs.docker.com/compose/install/)

### Installation & Setup

You can set up and run the entire application using the single command block below. Just copy and paste it into your terminal.

Platforms like GitHub will automatically add a copy button to the top-right corner of the code block for convenience.

```bash
1. Clone the repository and navigate into the directory
git clone [https://github.com/Chhaviii03/VerbaTwin.git](https://github.com/Chhaviii03/VerbaTwin.git)
cd VerbaTwin

# 2. Create the environment file from the example
# (You can modify the .env file later if needed)
cp .env.example .env

# 3. Build and run the application with Docker Compose
# (This may take a few minutes on the first run as it downloads and builds the images)
docker-compose up --build
Your VerbaTwin API will now be running and available at http://localhost:5000.
```

To stop the application, press Ctrl + C in the terminal. To run it in the background next time, you can use docker-compose up -d.

⚙️ API Usage
The following are the primary endpoints available.

Calculate Similarity
Endpoint: POST /api/similarity

Description: Calculates and returns the semantic similarity score between two texts.

Request Body:
```bash
JSON

{
  "text1": "The sun is shining brightly today.",
  "text2": "It is a beautiful and sunny day."
}
```

Success Response (200 OK):
```bash
JSON

{
  "similarity_score": 0.93
}
```

Register User (Example)

Endpoint: POST /api/register

Description: Registers a new user and returns an API token for future authenticated requests.

Request Body:
```bash
JSON

{
  "username": "testuser",
  "password": "strongpassword123"
}
```
Success Response (201 Created):
```bash
JSON

{
  "message": "User registered successfully.",
  "api_token": "your_generated_api_token_here"
}
```
