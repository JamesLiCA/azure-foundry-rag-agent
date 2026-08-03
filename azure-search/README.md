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
