# RAG Research Assistant

A Retrieval-Augmented Generation (RAG) research assistant built in Google Colab during a hands-on Agentic AI workshop organized by BIT IEEE Computer Society in association with the Department of CSE at Bangalore Institute of Technology, in collaboration with Paytm.

## Overview

This project lets users ask questions about three AI research papers. It retrieves semantically relevant text chunks and passes them to a large language model (LLM), which generates an answer grounded in the retrieved context.

## Research Papers

- Attention Is All You Need — arXiv:1706.03762
- Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks — arXiv:2005.11401
- ReAct: Synergizing Reasoning and Acting in Language Models — arXiv:2210.03629

## How It Works

1. Downloads the research papers from arXiv.
2. Extracts text from the PDFs using pypdf.
3. Splits text into overlapping chunks.
4. Generates normalized embeddings using Sentence Transformers (`all-MiniLM-L6-v2`).
5. Indexes the embeddings in FAISS for similarity search.
6. Retrieves the top matching chunks for a question.
7. Sends the question and retrieved context to an LLM through the Groq API.
8. Returns an answer with source chunk references.

## Technology Stack

- Python
- Google Colab
- Sentence Transformers
- FAISS
- PyPDF
- NumPy
- arXiv API
- Groq API
- `openai/gpt-oss-120b` (model configured in the original notebook; availability may change)

## Run the Project

1. Open the notebook in Google Colab.
2. Install the required dependencies: `sentence-transformers`, `faiss-cpu`, `pypdf`, `groq`, `arxiv`, and `requests`.
3. Provide your own Groq API key when prompted. Never commit API keys to the repository.
4. Run the cells in order to download the papers, build the vector index, and query the research assistant.

API access, model availability, and usage limits depend on your Groq account and current provider policies.

## Limitations

- Answers depend on the text successfully extracted from the PDFs and the chunks retrieved by semantic search.
- Source references identify retrieved chunks; they are not independently verified page-level citations.
- The system may still produce incorrect or incomplete answers, so important claims should be checked against the original papers.
- The current implementation is a RAG question-answering pipeline, not a fully autonomous agent.

## Learning Outcomes

- PDF text extraction and text chunking
- Semantic embeddings and vector similarity search
- FAISS-based retrieval
- Context-grounded LLM prompting
- Basic RAG pipeline design

## Acknowledgment

Built as a hands-on project during the Agentic AI Workshop held at Bangalore Institute of Technology on 28 September 2026, organized by BIT IEEE Computer Society with the Department of CSE and in collaboration with Paytm.
