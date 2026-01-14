Wikipedia Semantic Search Pipeline
Azure Databricks · Azure Storage · Pinecone
Overview
This document describes a semantic search data pipeline built on Wikipedia data using Azure Databricks, Azure Storage, transformer-based embeddings, and Pinecone as a vector database.

The implementation focuses on data ingestion, processing, embedding generation, and vector indexing. It provides the foundational retrieval layer required for semantic search systems.

Scope clarification: This project implements semantic retrieval only. 
Architecture
Wikipedia XML Dump
→ Azure Storage (Raw XML)
→ Azure Databricks (Spark ETL & Cleaning)
→ Text Embeddings (Sentence Transformers)
→ Pinecone Vector Index
→ Semantic Similarity Search
Notebooks Included
06-Process-Wikipedia.ipynb
Processes Wikipedia XML dumps using Spark. Extracts article titles and text, removes wiki markup and references, and outputs cleaned structured data.

07-Wikipedia-Embeddings.ipynb
Generates semantic embeddings using the all-MiniLM-L6-v2 Sentence Transformer model. Produces 384-dimensional vectors for each article.

08-Upload-Wikipedia-Pinecone.ipynb
Uploads embeddings to Pinecone with associated metadata and enables cosine-similarity based semantic search.

Technology Stack
Cloud Platform: Microsoft Azure (Azure Databricks, Azure Storage)
Data Processing: Apache Spark (PySpark)
Embeddings: Sentence Transformers (all-MiniLM-L6-v2)
Vector Database: Pinecone
Programming Language: Python

Execution Order
1. Upload all notebooks to Azure Databricks
2. Configure Azure Storage and Pinecone credentials
3. Run notebooks in order:
   a. 06-Process-Wikipedia.ipynb
   b. 07-Wikipedia-Embeddings.ipynb
   c. 08-Upload-Wikipedia-Pinecone.ipynb

   

