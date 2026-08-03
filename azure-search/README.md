# Azure AI Search Configuration

This folder contains the Azure AI Search resources used by the AUCHDAS Customer Service Agent.

The search service provides:

- Document ingestion
- Intelligent chunking
- Vector embedding generation
- Hybrid retrieval
- Semantic ranking
- Vector search
- Retrieval-Augmented Generation (RAG)

## Components

| File | Purpose |
|-------|----------|
| datasource.json | Connects Azure Blob Storage |
| skillset.json | Document cracking and embedding |
| index-schema.json | Search index definition |
| indexer.json | Runs the ingestion pipeline |

## Embedding Model

OpenAI

text-embedding-3-small

1536 dimensions

Cosine similarity

## Search Features

- Hybrid Search
- Semantic Ranking
- Vector Search (HNSW)
- Metadata Filtering

# Azure AI Search Components

This folder contains the Azure AI Search resources used by the AUCHDAS AI Customer Service Agent.

---

## datasource.json

Purpose:

Connect Azure Blob Storage to Azure AI Search.

Documents:

- Product Catalog
- User Manual
- FAQ
- Warranty
- Installation Guide

---

## skillset.json

Responsible for:

- Document cracking
- Chunking
- Embedding generation
- Metadata enrichment

Pipeline:

Blob Storage
↓

Extract Text
↓

Chunk Text
↓

Generate Embeddings
↓

Store Metadata

---

## index-schema.json

Defines:

- Searchable fields
- Metadata fields
- Vector field
- Semantic configuration
- HNSW vector search

---

## indexer.json

Responsible for:

- Reading documents
- Executing skillset
- Populating vector index
