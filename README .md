# Building an Effective Search System – HelpMateAI

## 1. Overview
This project illustrates how to build an **effective generative search system** using RAG (Retrieval Augmented Generation) techniques. The focus is on answering queries derived from a comprehensive life insurance policy document.

## 2. Objective
The main objective is to design a **robust and accurate generative search system** that can interpret and answer questions from a large, complex insurance policy document.

## 3. Reference Document
- The policy file is available here: [Principal-Sample-Life-Insurance-Policy.pdf]

## 4. Methodology
The solution is structured into three main layers, each playing a critical role. Multiple strategies should be explored within these layers to optimize the final outcome.

### a. Embedding Layer
- Preprocess, clean, and chunk the policy document before embedding.
- Choose an appropriate chunking method, as this significantly impacts retrieval quality.
- Experiment with embedding models such as **OpenAI embeddings** or **SentenceTransformers (HuggingFace)**.

### b. Search Layer
- Design at least three representative queries based on the insurance document.
- Embed these queries and perform retrieval from the **ChromaDB vector database**.
- Implement a caching mechanism for query efficiency.
- Enhance results with **cross-encoder re-ranking** to ensure relevance.

### c. Generation Layer
- Construct a carefully designed prompt that integrates retrieved context.
- Ensure instructions are comprehensive and relevant details are included.
- Optionally, apply **few-shot examples** to strengthen answer quality.

## 5. System Components
- **Reading & Processing PDF:** Use [pdfplumber](https://pypi.org/project/pdfplumber/) to extract structured data, including text, tables, and images.
- **Document Chunking:** Implement fixed-size chunking as a baseline, with potential optimizations.
- **Embedding Generation:** Generate embeddings with **SentenceTransformer (all-MiniLM-L6-v2)**.
- **ChromaDB Storage:** Save embeddings efficiently for fast retrieval.
- **Semantic Search + Cache:** Introduce a caching mechanism for performance optimization.
- **Re-Ranking:** Apply cross-encoder models to refine search relevance.
- **Retrieval-Augmented Generation:** Use **GPT-3.5** with structured prompts to provide final answers with citations.

## 6. System Architecture
![System Architecture](./architecture.png)

## 7. Prerequisites
- **Python 3.7+**
- Add your **OpenAI API Key** in the `OpenAI_API_Key` file to enable API access.

## 8. Query Demonstrations
![Query & Answers](./queries-answer.png)
