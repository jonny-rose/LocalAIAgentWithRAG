# Project: Local AI Agent with Retrieval-Augmented Generation (RAG)

This project implements a local AI agent designed to answer user questions about a pizza restaurant by leveraging **Retrieval-Augmented Generation (RAG)**. The system combines a language model with a vector database to provide contextually relevant answers based on restaurant reviews.

## Key Components

### Language Model (LLM)
- Utilizes the `OllamaLLM` model (`llama3.2`) for generating responses.
- Processes user queries and generates answers based on retrieved context.

### Prompt Template
- A predefined prompt guides the LLM to act as an expert in answering questions about a pizza restaurant.
- Includes placeholders for reviews and user questions.

### Vector Database (ChromaDB)
- Stores embeddings of restaurant reviews for efficient similarity search.
- Uses `OllamaEmbeddings` to generate embeddings for the reviews.
- Retrieves the top 5 most relevant reviews for a given user query.

### Data Source
- Reads restaurant reviews from a CSV file (`realistic_restaurant_reviews.csv`).
- Each review includes metadata such as title, review content, rating, and date.

### Interactive CLI
- Provides a command-line interface for users to input questions.
- Continuously processes user queries until the user decides to quit.

## Workflow

### Data Preparation
- Reviews are read from the CSV file and converted into embeddings.
- The embeddings are stored in a persistent ChromaDB instance.

### Query Processing
- User inputs a question via the CLI.
- The system retrieves the most relevant reviews from the vector database.
- The LLM generates a response using the retrieved reviews as context.

### Output
- The generated response is displayed to the user.

## Files

- `main.py`: Contains the main logic for the interactive CLI and LLM integration.
- `vector.py`: Handles vector database setup, embedding generation, and review retrieval.
- `realistic_restaurant_reviews.csv`: The dataset of restaurant reviews.
- `chrome_langchain_db/`: Persistent storage for the vector database.