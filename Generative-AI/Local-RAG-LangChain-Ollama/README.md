# Local RAG Document Q&A using LangChain, Ollama and FAISS

## Overview

This project demonstrates a basic Retrieval-Augmented Generation (RAG)
application built using LangChain, Ollama and FAISS.

The application loads a text document, splits it into smaller chunks,
converts the chunks into embeddings, stores them in a FAISS vector
database, retrieves relevant information using similarity search,
and generates an answer using the Gemma 2B language model.

## RAG Workflow

Document
   ↓
TextLoader
   ↓
Text Splitting
   ↓
Ollama Embeddings
   ↓
FAISS Vector Store
   ↓
Similarity Search
   ↓
Relevant Context
   ↓
Gemma 2B
   ↓
Final Answer

## Technologies Used

- Python
- LangChain
- Ollama
- FAISS
- Jupyter Notebook

## Models Used

### Embedding Model

`nomic-embed-text`

Used to convert text chunks into numerical vectors.

### Language Model

`gemma:2b`

Used to generate answers using the retrieved document context.

## Project Steps

### 1. Document Loading

The project loads a text document using LangChain's `TextLoader`.

### 2. Text Splitting

The document is divided into smaller chunks using
`RecursiveCharacterTextSplitter`.

Example configuration:

- Chunk size: 500
- Chunk overlap: 50

### 3. Embeddings

The text chunks are converted into vector representations using
Ollama's `nomic-embed-text` model.

### 4. Vector Store

The embeddings are stored in a FAISS vector database.

### 5. Similarity Search

When a user asks a question, FAISS performs similarity search and
retrieves the most relevant document chunks.

### 6. Response Generation

The retrieved chunks are provided as context to the Gemma 2B model,
which generates the final answer.

## Example

Question:

"What is artificial intelligence?"

The system retrieves relevant information from the document and
provides an answer based on the retrieved context.

## Project Structure

```text
Local-RAG-LangChain-Ollama/
│
├── data/
│   └── speech.txt
│
├── rag_project.ipynb
│
├── requirements.txt
│
└── README.md
