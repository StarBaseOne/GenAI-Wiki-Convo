# GenAI-Wiki-Convo

GenAI-Wiki-Convo is a project built on the DataStax WikiChat demo aimed at providing a conversational interface for querying Wikipedia content in a natural language format. It is intended to be an iteration of the DataStax project with additional features (as show in the feature section). It offers real-time updates, intelligent question generation, and accurate responses.

## Problem Statement and Purpose

- The project addresses the inconvenience of users needing to navigate through search engine results and Wikipedia pages to find information.
- The purpose is to democratize knowledge by providing a conversational interface directly to Wikipedia content.

## Architecture

- **Data Ingestion**: Initial data is loaded by scraping the top 1000 Wikipedia articles and then listening to real-time updates via Wikipedia's Event Stream.
- **Data Storage**: Utilizes Astra DB to store metadata, chunks of articles, and suggestions.
- **Conversational UX**: Built on Next.js and Vercel's AI library, with Cohere and OpenAI for language processing.
- **Technologies Used**: Next.js, LangChain, Vercel, OpenAI, Cohere, and DataStax Astra DB.

## Setup

- Requires accounts for Astra DB, Cohere, and OpenAI.
- Involves setting up environment variables and configurations for these services.

## Data Ingestion

- Python scripts handle data ingestion, including scraping, text chunking, calculating embeddings, and storing in Astra DB collections.
- Asynchronous processing ensures continuous updates while handling bursts of data from Wikipedia.

## Chatbot User Experience

- Utilizes Vercel's AI npm library for the chat interface.
- Offers suggestions based on recently updated Wikipedia pages.
- Implements a sequence of actions to process user questions, retrieve relevant data, and generate responses.

## Pre-populating Suggested Questions

- Utilizes LangChain to generate suggested questions based on recent Wikipedia updates.
- Queries Astra DB for recent articles and constructs prompts for the OpenAI model to generate questions.

## Using RAG to Answer Questions

- Utilizes LangChain's capabilities to interact with Cohere for embeddings and OpenAI for generating responses.
- Implements a chain of operations to process user questions, retrieve context, and generate accurate responses.

## Additional Features

- List Here
