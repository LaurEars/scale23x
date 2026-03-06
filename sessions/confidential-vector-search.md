# Confidential Vector Search: Knowledgebase Homomorphic Encryption

https://www.socallinuxexpo.org/scale/23x/presentations/confidential-vector-search-knowledgebase-homomorphic-encryption

- **Date**: Thursday, March 5, 2026
- **Time**: 14:40 - 15:00
- **Location**: Ballroom F
- **Speaker(s)**: Sulimon Sattari

> "Confidential Vector Search: Knowledgebase Homomorphic Encryption" introduces a practical path to RAG systems that can search sensitive embeddings without ever revealing them. Building on the SIAM study "Maturing Homomorphic Encryption (HE) to Enable Privacy Preserving Vector Search," the presentation unpacks how techniques like dimensional scrambling, noise injection, CKKS, and chaotic mapping combine with schemes such as DIEHARD and ROME to preserve inner products while keeping queries and documents encrypted. The session translates mathematical concepts into system design: encrypting a knowledge base on untrusted infrastructure, conducting similarity searches directly in ciphertext space, and achieving usable performance for real-time applications. The discussion covers threat models, benchmark comparisons of different HE approaches, and integration pathways for personal AI and healthcare scenarios where confidentiality is critical.

## Overview

A practical walkthrough of homomorphic encryption techniques for building RAG systems that perform vector similarity search entirely in ciphertext space, never exposing the underlying data.

## Key Points

- Operate on the data without decrypting it
- Scramble elements in vector -> same dot product calculated in RAG
- 2025 SIAM Mathematical Problems in Industry Workshop to solve issue w/ ~15 mathematicians
- Kwaai github has code and paper is available
