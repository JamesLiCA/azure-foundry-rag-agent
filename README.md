# Multilingual RAG and AI Customer-Service Agent on Microsoft Azure

This project demonstrates an end-to-end Retrieval-Augmented Generation and AI Agent solution built with Microsoft Foundry and Azure AI services.

The proof of concept uses product catalogues, user manuals, installation guidance, troubleshooting content, FAQs, pricing, and customer-service policies to provide grounded multilingual customer-support responses.

## Business Use Case

A range-hood retailer receives customer inquiries through online advertising and messaging channels. The objective is to provide an AI assistant that can:

- Answer product and pricing questions
- Recommend products based on customer needs
- Explain installation and maintenance requirements
- Support troubleshooting and warranty questions
- Respond in English, Chinese, and French
- Ground responses in approved business documents
- Provide source citations
- Avoid unsupported or fabricated answers

## Solution Architecture

```text
Customer
   |
   v
Microsoft Foundry Agent
   |
   v
Foundry IQ Knowledge Base
   |
   v
Azure AI Search
   |
   +-- BM25 keyword search
   +-- Semantic ranking
   +-- HNSW vector search
   |
   v
Azure OpenAI Embeddings
text-embedding-3-small
   |
   v
Azure Blob Storage
   |
   +-- Product catalogue
   +-- User manual
   +-- Installation guide
   +-- FAQ and troubleshooting
   +-- Customer-service policy
```

## Azure Services Used

- Microsoft Foundry
- Microsoft Foundry Agent Service
- GPT-5
- Foundry IQ Knowledge Base
- Azure AI Search
- Azure OpenAI `text-embedding-3-small`
- Azure Blob Storage
- Azure Role-Based Access Control
- Managed identities

## RAG Ingestion Pipeline

1. Documents are stored in Azure Blob Storage.
2. An Azure AI Search data source connects to the Blob container.
3. A skillset extracts and splits document content.
4. Each chunk is converted into a 1,536-dimensional embedding.
5. Text, metadata, and vectors are stored in Azure AI Search.
6. The index supports BM25, semantic ranking, and HNSW vector retrieval.
7. Foundry IQ exposes the Search index to the AI Agent.
8. The Agent generates grounded multilingual responses with citations.

## Key Capabilities

- Retrieval-Augmented Generation
- Vector and semantic search
- Hybrid retrieval
- Grounded answers with citations
- Multilingual customer support
- Product recommendation
- Installation and troubleshooting guidance
- Hallucination reduction
- Managed-identity authentication
- Azure RBAC security
- Agent testing through Microsoft Foundry

## Demonstrated Results

The current proof of concept:

- Ingested five business documents
- Generated 15 searchable document chunks
- Successfully indexed all documents with zero indexing errors
- Retrieved product prices and documentation through Azure AI Search
- Generated grounded answers with source citations
- Responded successfully in English and Chinese
- Exposed the Agent through a Foundry preview web application

## Example Questions

```text
What is the price of the AUC-9036-W?

Compare two AUCHDAS range-hood models.

What should I confirm before installation?

这个产品多少钱？

Comment installer cette hotte?
```

## Security Design

- Azure AI Search uses managed identity to read from Blob Storage.
- Azure AI Search uses managed identity to call the embedding model.
- The Foundry project identity has read access to the Search index.
- Secrets and API keys are not stored in this repository.
- Public screenshots are sanitized to remove subscription IDs, keys, and customer information.

## Current Scope

This repository documents a functional proof of concept. It is not presented as a production deployment.

The current system uses static product and pricing documents. Live inventory, order status, installation booking, and Facebook Messenger integration are planned enhancements.

## Planned Enhancements

- Facebook Messenger webhook integration
- Automatic language translation for a Chinese-speaking operator
- Live inventory and pricing API tools
- Human approval workflow
- Specialized sales, installation, and warranty agents
- Prompt-injection protection
- Automated evaluation and monitoring
- Conversation memory
- CI/CD and infrastructure as code

## Disclaimer

The installation guide used in this proof of concept is general demonstration content. Product-specific installation, electrical, gas, structural, and safety work should be verified using manufacturer documentation and qualified professionals.

## Author

James Li

AI, Data, Cloud, and Cybersecurity Architect
