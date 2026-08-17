# Semantic PDF Search & Question Answering

A **Retrieval-Augmented Generation (RAG)** based system for querying information from PDF documents using **LangChain, OpenAI, and Astra DB Vector Search**.

## Overview

This project implements a PDF question-answering pipeline that extracts text from a PDF, generates vector embeddings, stores them in **Astra DB**, and retrieves relevant content to generate answers using an LLM.

The system combines **semantic search and LLM-based question answering** to provide context-aware responses from the uploaded document.

## Architecture

```text
PDF Document
     ↓
PyPDF2
     ↓
Text Extraction
     ↓
OpenAI Embeddings
     ↓
Astra DB Vector Search
     ↓
Similarity Search
     ↓
Relevant Document Context
     ↓
OpenAI LLM
     ↓
Generated Answer
```

## Key Features

* Extracts text from PDF documents using **PyPDF2**
* Generates document embeddings using **OpenAI Embeddings**
* Stores and retrieves embeddings using **Astra DB Vector Search**
* Uses **LangChain** to connect retrieval and LLM components
* Performs similarity search to identify relevant document content
* Generates answers using an **OpenAI LLM**

## Technologies Used

* **Python**
* **LangChain**
* **PyPDF2**
* **OpenAI**
* **Astra DB**
* **Cassandra Vector Search**
* **Vector Embeddings**
* **Retrieval-Augmented Generation (RAG)**

## How It Works

### 1. PDF Text Extraction

The PDF document is loaded using `PyPDF2`, and text is extracted from its pages.

### 2. Embedding Generation

The extracted content is converted into vector representations using **OpenAI Embeddings**.

### 3. Vector Storage

The embeddings are stored in an **Astra DB Cassandra vector store**, enabling semantic similarity search.

### 4. Retrieval

When a user enters a question, the system performs similarity search to retrieve the most relevant document content.

### 5. Answer Generation

The retrieved context is passed to an **OpenAI LLM** through LangChain to generate the final answer.

## Example

The system accepts questions through an interactive question-answering loop:

```text
Enter your question: <your question>

QUESTION: "<your question>"
ANSWER: "<generated answer>"
```

The system also displays the most relevant retrieved documents along with their similarity scores.

## Installation

Clone the repository:

```bash
git clone https://github.com/<YOUR_USERNAME>/semantic-pdf-search-rag.git
cd semantic-pdf-search-rag
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

The project requires:

* Astra DB Application Token
* Astra DB Database ID
* OpenAI API Key

Store these credentials securely as environment variables. **Do not hard-code API keys or commit them to GitHub.**

## Project Structure

```text
semantic-pdf-search-rag/
│
├── PDFQuery_LangChain.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Future Improvements

* Add configurable text chunking and overlap strategies
* Evaluate retrieval quality using a labelled question set
* Add source/page-level citations to generated answers
* Develop a web interface using Streamlit or Gradio
* Experiment with locally hosted LLMs

## Project Status

**Completed:** Core PDF retrieval and question-answering pipeline using LangChain, OpenAI, and Astra DB Vector Search.
