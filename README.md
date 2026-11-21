# SENG 472 - Work@Home 4: Text-to-SQL Chatbot

## Project Overview

This project implements an LLM-powered chatbot that converts natural language questions in Turkish or English into SQL queries and retrieves information from the Northwind SQLite database.

The application uses structured JSON outputs to ensure consistent responses and validates generated SQL before execution.

## Technologies Used

- Python
- Groq API (GPT-OSS-20B)
- OpenAI-compatible Chat Completions API
- SQLite (Northwind Database)
- JSON Schema
- Pandas
- Jupyter Notebook (VS Code)

## How It Works

1. The user enters a question in Turkish or English.
2. The LLM generates a SQL query in structured JSON format.
3. The application checks whether the question is answerable and whether the SQL is allowed.
4. The SQL query is executed on the read-only SQLite database.
5. The query results are displayed using Pandas.

## How to Run

1. Install the required Python packages:

   `pip install openai pandas ipykernel python-dotenv`

2. Place `northwind.db` in the project directory.
3. Create a `.env` file and add your Groq API key:

   `GROQ_API_KEY=your_api_key`

4. Open `chatbot.ipynb` in VS Code.
5. Select your Python environment and run the notebook cells in order.
6. Enter questions in Turkish or English. Type `exit` to stop.

## Example Questions

- How many customers are there?
- En fazla sipariş veren ilk 5 müşteriyi listele.
- Which employee has handled the highest number of orders?
- Hangi ürün kategorisinde kaç ürün bulunuyor?
- Delete all customers from the database.

The last example demonstrates how the application rejects data modification requests.

## Security

The database is opened in read-only mode. The chatbot is instructed to generate only SELECT queries, and basic SQL validation is performed before execution.

API keys are stored in a `.env` file and excluded from Git using `.gitignore`.

## Course Information

**Course:** SENG 472 - Building AI Applications with Large Language Models  
**Assignment:** Work@Home 4