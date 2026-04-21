# Local RAG System for Secure Document Retrieval

## Project Overview
This project implements a **Fully Local Retrieval-Augmented Generation (RAG)** architecture. It is designed to solve the problem of "knowledge cutoffs" and "hallucinations" in LLMs by grounding the model in a specific, private dataset—in this case, the **Department of Foreign Affairs (DFA) Home Office Operations Manual**.

By running entirely on local hardware, this system ensures data privacy and security, making it ideal for institutional or sensitive government documentation.

## Key Features
- **Model:** [Phi-3-mini-4k-instruct](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct) (Lightweight & High Performance).
- **Vector Database:** FAISS (Facebook AI Similarity Search) for efficient dense retrieval.
- **Embeddings:** BGE-Large-EN-v1.5 for high-precision semantic mapping.
- **Data Source:** DFA Operations Manual (Authentication Division).
- **Privacy:** No external APIs or cloud processing used during inference.

## Methodology
1. **Document Processing:** PDF parsing and recursive character chunking to maintain context.
2. **Indexing:** Generating semantic embeddings and storing them in a FAISS index.
3. **Retrieval:** Top-K similarity search to fetch relevant context for user queries.
4. **Generation:** Context-injected prompting to the Phi-3 model for fact-grounded answers.

## Project Structure
- `Final_AI3_ipynb.ipynb`: The complete Python implementation of the RAG pipeline.
- `IEEE3 Paper - AI3 Kitkat.pdf`: The full technical research paper explaining the architecture and evaluation.
- `DFA_Operations_Manual-1.pdf`: The primary knowledge base used for testing.

## Evaluation Results
The system was evaluated using:
- **Recall@K & Precision@K:** To measure retrieval accuracy.
- **Faithfulness Scoring:** Using sentence-level similarity to ensure the model does not hallucinate beyond the provided text.

## Authors
- **Leila Janine Villegas** - Mapúa University
- **Prince Jeffery Villamil** - Mapúa University
- **Liandro Refulle** - Mapúa University
