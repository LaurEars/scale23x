# OpenSearch: Your Friendly Neighborhood Vector Database

https://www.socallinuxexpo.org/scale/23x/presentations/opensearch-your-friendly-neighborhood-vector-database

- **Date**: Sunday, March 8, 2026
- **Time**: 13:45 - 14:45
- **Location**: Ballroom DE
- **Speaker(s)**: Navneet Verma, Principal Engineer, AWS; Naveen Tatikonda, Software Development Engineer, Amazon Web Services

> The presentation explores OpenSearch's capabilities as a vector database. The speakers will demonstrate "the progress we've made here at the OpenSearch project implementing vector database operations" and making them accessible to developers. Content covered includes creating and querying vector embeddings, implementing semantic search, and preparing for RAG applications. Described as "OpenSearch Vector Operations for Dummies," the session aims to "bring a user-friendly path on a battle tested, fully open source platform."

## Overview

A beginner-friendly walkthrough of OpenSearch as a vector database, covering embedding creation, semantic search, and RAG application patterns on a battle-tested open-source platform.

## Key Points

- Vectors capture semantic meaning and relationships
- Each shard is one lucene index
- Each shard/lucene index has segments
- Each segment has .fdt .dvd .tim etc for an index eg .faiss
- Vector search lands on coordinator → coordinator searches all shards
- Define vector field, type of `"knn_vector"`, define dimensions (length) and `"space_type"`
- Semantic search, not only lexical search
- Evolution of search
  - Lexical
  - Semantic
  - Hybrid
  - Agentic
- Opensearch k-NN plugin
- Two ways to search
  - Exact k-NN (brute force)
  - Approximate k-NN (ANN) with HNSW/IVF algorithms
- Approximate k-NN algorithms
  - Hierarchical Navigable Small World (HNSW)
  - Inverted File Structure (IVF) – breaks vectors into centroids for faster searching
  - Comparison of IVF and HNSW
    - HNSW graph based vs cluster based
    - High memory vs memory-constrained
    - HNSW superior for recall quality
- Radial search
- Multi-vector and nested search: good for multi-view search with multiple vectors
- Hardware acceleration via opensearch hardware
- k-NN filtering
  - Pre-filtering: filter then vector search
  - Post-filtering: vector search then filter
  - Efficient filtering: filter, intelligent k-NN search
- Hybrid search: Score-based and rank based approaches
- Agentic search: generate queries from natural language to get results
- VectorDB: The brain and memory of AI search
  - Semantic memory
  - Working memory
  - Long-term memory
  - Episodic memory
- How to scale vector search
  - Disk optimized search: reduces memory via quantization. Search on compressed vectors, then full-precision vectors
  - Accelerated vector engine with GPUs: 9.39x faster than CPU. Cheaper too

## Resources Mentioned

- [Scaling neural sparse search to billions of vectors](https://opensearch.org/blog/scaling-neural-sparse-search-to-billions-of-vectors-with-approximate-search/)
- [Using OpenSearch as a Vector Database](https://opensearch.org/blog/using-opensearch-as-a-vector-database/)
- [Save up to 2x on storage with derived source](https://opensearch.org/blog/save-up-to-2x-on-storage-with-derived-source/)
- [Reduce costs with disk-based vector search](https://opensearch.org/blog/reduce-cost-with-disk-based-vector-search/)
- [Building effective hybrid search in OpenSearch](https://opensearch.org/blog/building-effective-hybrid-search-in-opensearch-techniques-and-best-practices/)
- [GPU-accelerated vector search in OpenSearch: A new frontier](https://opensearch.org/blog/gpu-accelerated-vector-search-opensearch-new-frontier/)
