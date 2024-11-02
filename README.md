# semantic_chunk_RAG

# Semantic RAG Chain with LangChain and Groq

This repository demonstrates how to build a Retrieval Augmented Generation (RAG) chain using LangChain, Groq, and semantic chunking for improved context retrieval.

## Overview

This RAG pipeline leverages the power of semantic chunking to break down a PDF document into meaningful units based on sentence embeddings. This allows for more accurate and relevant retrieval of information when answering user queries. 

The pipeline uses the following key components:

* **LangChain:**  Provides the framework for building the RAG chain, including document loading, text splitting, and retrieval components.
* **Groq:**  A high-performance vector database used to store and query the semantically chunked document.
* **Hugging Face Embeddings:**  Utilizes the `sentence-transformers/all-MiniLM-L6-v2` model to generate sentence embeddings for semantic chunking.
* **RAGAS:**  Evaluates the performance of the RAG chain using metrics like faithfulness, answer relevancy, context precision, and context recall.

## Pipeline Steps

1. **Document Loading:** Loads a PDF document using `PyPDFLoader`.
2. **Semantic Chunking:** 
    * Splits the document into semantic chunks using `SemanticChunker` from `langchain_experimental`.
    * Employs Hugging Face embeddings to capture the semantic meaning of the text.
3. **Vector Store Creation:** Stores the semantic chunks in a Chroma vector database using `langchain_groq`.
4. **Retrieval:** Retrieves relevant context from the Groq database using `semantic_chunk_retriever`.
5. **Answer Generation:** Generates answers using a `ChatGroq` language model, conditioned on the retrieved context and user query.
6. **Evaluation:** Evaluates the RAG pipeline using RAGAS and a synthetic dataset, assessing key metrics like faithfulness and answer relevancy.

## Evaluation

The RAG chain is evaluated using RAGAS and a synthetic dataset generated using the pipeline's own components. This dataset is converted into Hugging Face dataset format for seamless integration with RAGAS. The evaluation focuses on the following metrics:

* **Faithfulness:** Measures how well the generated answer aligns with the provided context.
* **Answer Relevancy:**  Assesses the relevance of the generated answer to the user's query.
* **Context Precision:**  Evaluates the precision of the retrieved context in relation to the query.
* **Context Recall:** Measures the recall of the retrieved context.

## Key Features

* **Semantic Chunking:**  Improves context retrieval by dividing the document based on meaning rather than arbitrary character limits.
* **Groq Integration:** Leverages the speed and efficiency of Groq for storing and querying semantic chunks.
* **Comprehensive Evaluation:**  Uses RAGAS and a synthetic dataset to thoroughly assess the performance of the RAG chain.

## Getting Started
Use the notebok for practice
