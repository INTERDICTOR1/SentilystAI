# SentilystAI
SentilystAI is an AI-powered sentiment analysis platform tailored specifically for brokerage platforms and retail investors. By analyzing market news in real-time, SentilystAI provides actionable insights and personalized sentiment scores for stock portfolios. Our goal is to enable investors to make informed decisions based on the latest market sentiment data.
Table of Contents

    About SentilystAI
    Features
    Getting Started
    Installation
    Usage
    API Documentation
    Data Collection and Sources
    Sentiment Analysis
    Contributing
    License
    Contact

About SentilystAI

SentilystAI is a B2B SaaS platform that provides advanced AI-driven sentiment analysis for retail investors and brokerage platforms. By integrating with major trading platforms like Zerodha, Groww, and others, we aim to deliver real-time insights based on news articles related to user portfolios.

We leverage machine learning models to assess the sentiment of market-related news and provide users with personalized insights tailored to their specific stock portfolios.
Features

    Real-Time Sentiment Analysis: Evaluate and display sentiment scores for news articles as they are published.
    Personalized Insights: Portfolio-based sentiment analysis specific to user investments.
    Partnership with Brokerage Platforms: Offering seamless integration with popular brokerage platforms for in-depth market insights.
    Customizable Dashboards: Allowing users to view market sentiment data in an intuitive and customizable interface.
    Sentiment-Driven Alerts: Notifications on major market movements and shifts in stock sentiment.
    Historical Sentiment Tracking: Access to historical sentiment data to evaluate trends and make more informed decisions.

Getting Started
Prerequisites

To get started with SentilystAI, you need:

    Python 3.9 or higher
    Node.js (for the frontend)
    PostgreSQL (for the database)
    SentilystAI Model 1.0.0

Installation

Clone the repository:

bash

    git clone https://github.com/YourUsername/SentilystAI.git
    cd SentilystAI

Backend Setup (Flask)

    Create and activate a Python virtual environment:

bash

    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`

Install the required Python packages:

bash

    pip install -r requirements.txt

Set up the PostgreSQL database:

bash

    psql -U postgres -c "CREATE DATABASE sentilyst_db;"

Configure your environment variables (e.g., in a .env file):

bash

    DATABASE_URL=postgresql://username:password@localhost:5432/sentilyst_db
    FLASK_ENV=development
    SECRET_KEY=your_secret_key

Run the migrations and start the backend server:

bash

    flask db upgrade
    flask run

Frontend Setup (React)

Navigate to the client directory and install the frontend dependencies:

bash

    cd client
    npm install

Start the React development server:

bash

    npm start

Usage

Once the backend and frontend servers are running, open your browser and navigate to http://localhost:3000 to access the SentilystAI dashboard.
Key Functionalities:

    Dashboard: View sentiment analysis for stocks in real-time.
    News Feed: Aggregated news related to the stocks in your portfolio, with sentiment scores displayed for each article.
    Alerts: Receive personalized alerts on major sentiment shifts for the stocks you're following.
    Historical Data: Analyze trends with past sentiment scores for selected stocks.

API Documentation

The SentilystAI API allows developers to integrate sentiment analysis into their applications. Below is a brief overview of the available API endpoints:
Sentiment Analysis API
GET /api/sentiment

Retrieve the sentiment score for a given stock or news article.

bash

    curl -X GET "http://localhost:5000/api/sentiment?stock=AAPL"

    Parameters:
        stock: The stock ticker symbol (e.g., AAPL).
        article_id: The ID of the news article.

    Response:

    json

    {
      "stock": "AAPL",
      "sentiment": "positive",
      "score": 0.87
    }

Portfolio API
POST /api/portfolio

Add or update a user’s portfolio.

bash

    curl -X POST "http://localhost:5000/api/portfolio" \
        -H "Content-Type: application/json" \
        -d '{"user_id": 1, "portfolio": ["AAPL", "GOOGL", "TSLA"]}'

Data Collection and Sources

SentilystAI collects and processes data from various news sources, including:

    Quantexa API
    Aylien API
    Yahoo Finance

Data is fetched in real-time, and articles are analyzed using our fine-tuned machine learning model to assess the overall sentiment.
Sentiment Analysis

We use a fine-tuned version of FinBERT, a transformer-based model trained on financial data, to predict the sentiment of news articles. The sentiment can be classified as positive, neutral, or negative, with additional intensity scores ranging from 0 to 1. The platform uses several metrics, including time decay and weighted sentiment scores, to provide actionable insights.
Sentiment Scoring Formula

Our sentiment analysis engine uses a proprietary scoring formula that includes:

    Sentiment Intensity: A measure of how strongly positive or negative an article is.
    Time Decay: Older news articles have less impact on the overall score.
    Portfolio Weighting: Articles related to stocks in a user's portfolio are weighted more heavily.

Contributing

Contributions are welcome! If you'd like to contribute to SentilystAI, please follow these steps:

    Fork the repository.
    Create a new branch for your feature or bug fix.
    Commit your changes.
    Push to your branch and create a pull request.

Before submitting a pull request, ensure that your code passes all tests and follows the project's coding guidelines.
License

SentilystAI is licensed under the MIT License.
Contact

For any inquiries or support, please contact us at:

    Email: support@sentilystai.com
    Website: SentilystAI
    LinkedIn: SentilystAI on LinkedIn
