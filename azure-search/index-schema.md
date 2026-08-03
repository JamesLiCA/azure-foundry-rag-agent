# Azure AI Search Index

This index stores all document chunks generated from AUCHDAS documentation.

## Features

- Hybrid Search
- Semantic Search
- Vector Search
- HNSW algorithm
- Azure OpenAI embeddings

## Key Fields

| Field | Purpose |
|--------|---------|
| chunk_id | Unique chunk identifier |
| title | Document title |
| content | Chunk text |
| content_vector | Vector embedding |
| source_file | Original document |
| document_type | Manual, FAQ, Pricing, Warranty |
| language | Document language |
| page_number | Source page |

## Embedding Model

Azure OpenAI

text-embedding-3-small

1536 dimensions

Cosine similarity
