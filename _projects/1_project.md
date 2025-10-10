---
layout: page
title: Agentic RAG Chatbot for LegalQA
description: Inter IIT Tech Meet 13.0 - Rank 4 among 23 IITs
img: assets/img/legal-ai.jpg
importance: 1
category: research
github: https://github.com/himanshu-skid19
---

## Overview

Developed an advanced Retrieval-Augmented Generation (RAG) system specifically designed for legal question answering that addresses the critical problem of hallucination and inaccurate information retrieval in legal AI systems.

## Problem Statement

Legal RAG systems often suffer from:
- **Hallucination**: Generating false or misleading legal information
- **Inaccurate Retrieval**: Retrieving irrelevant or contextually incorrect legal documents
- **Real-time Constraints**: Need for immediate, accurate responses in legal scenarios

## Technical Approach

### 1. Parallel DAG-based Task Planning
- **Modified LLMCompiler**: Adapted the LLMCompiler framework to work specifically with RAG systems
- **Parallel Processing**: Implemented parallel task execution for faster response times
- **Dynamic Task Scheduling**: Intelligent scheduling based on query complexity and document availability

### 2. Real-time Data Processing
- **Pathway's Vector Store**: Integrated Pathway's vector database for real-time document ingestion
- **Dynamic Retrieval**: System can handle new legal documents as they're added
- **Scalable Architecture**: Built to handle large-scale legal document repositories

### 3. Advanced Retrieval Mechanisms
- **Multi-stage Retrieval**: Implemented hierarchical retrieval with multiple filtering stages
- **Context Preservation**: Maintained legal context throughout the retrieval process
- **Relevance Scoring**: Custom scoring mechanism for legal document relevance

## Results & Impact

### Performance Metrics
- **86% accuracy** on the CUAD dataset (contract law)
- **84% accuracy** on the AILA dataset (case law)
- **Rank 4** achievement among all 23 IITs at Inter IIT Tech Meet 13.0

### Key Achievements
- **Reduced Hallucination**: Significant improvement in factual accuracy for legal responses
- **Enhanced Reliability**: More trustworthy legal information retrieval
- **Real-time Performance**: Sub-second response times for most queries

## Technical Stack

- **Language Models**: Large Language Models with custom fine-tuning
- **Vector Database**: Pathway's vector store for real-time processing
- **Framework**: Modified LLMCompiler for parallel task execution
- **Evaluation**: CUAD and AILA datasets for comprehensive testing

## Future Work

- Integration with more legal databases
- Support for multilingual legal documents
- Enhanced explainability for legal reasoning
- Deployment for real-world legal assistance

This project demonstrates the potential of combining advanced AI techniques with domain-specific knowledge to create reliable, accurate systems for critical applications like legal assistance.