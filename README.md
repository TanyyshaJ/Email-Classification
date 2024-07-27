# Automatic Email Reply System for Film Equipment Rental Service

## Overview

The Automatic Email Reply System is designed to streamline communication for a film equipment rental service. It uses advanced natural language processing techniques to classify incoming emails and generate tailored responses. This system enhances customer interactions by automating responses to inquiries, reviews, and assistance requests.

## Features

- Automated email classification
- Dynamic response generation
- Integration with Pinecone for vector search
- Hybrid retrieval-augmented generation (RAG) pipeline

## RAG Pipeline

### Overview

The RAG (Retrieval-Augmented Generation) pipeline in this project is implemented as a hybrid system. It combines vector-based retrieval with keyword-based search to handle complex queries efficiently and accurately. This hybrid approach leverages the strengths of both methods to provide comprehensive responses.

### Components

- **Pinecone**: Used for efficient vector search and similarity retrieval.
- **Langchain**: Framework for managing retrieval-augmented generation processes and interfacing with language models.
- **HuggingFace Embeddings**: Generates dense vector representations of text.

### Pipeline Flow

1. **Initialization**:
   - Initialize Pinecone with an API key and configure the index for vector searches.
   - Integrate Langchain's retrieval capabilities for hybrid search using both vector and keyword-based approaches.

2. **Index Creation**:
   - Create an index named `email-classification` with dimensions (384 dimensions) suited for dense vector representations and configure it to use dot product as the metric.

3. **Embedding and Indexing**:
   - Embed texts using HuggingFace embeddings and index them in Pinecone for efficient retrieval.

4. **Hybrid Search**:
   - Employ PineconeHybridSearchRetriever to perform searches that leverage both dense vector representations and traditional keyword-based approaches. This hybrid search improves the accuracy of retrieval by considering both semantic meaning and explicit keywords.

### Benefits

The hybrid RAG pipeline ensures that the system handles a diverse range of queries with high precision. By integrating vector search with keyword search, it provides responses that are both contextually relevant and directly aligned with user queries. This approach is particularly effective for managing various email content related to equipment availability, similar items, and customer feedback.

## Installation

To get started, clone this repository and install the required dependencies:

```bash
git clone https://github.com/yourusername/automatic-email-reply-system.git
cd automatic-email-reply-system
```

## Usage

1. **Configuration**:
   - Set up your Pinecone API key and other configurations in the `config.yaml` file.

2. **Run the System**:
   - Execute the main script to start the email classification and response generation process:
     ```bash
     python main.py
     ```

## Acknowledgments

- **Pinecone**: For vector search capabilities.
- **Langchain**: For retrieval-augmented generation support.
- **HuggingFace**: For embedding models.
