# 1-Day Workshop: Building RAG Systems

## 1. Understanding the Problem (30 min)

### Enhancing AI with Knowledge

* Limitations of LLMs
* Hallucination Problem
* Knowledge Cutoff

### Why AI Needs External Knowledge

* Static vs Dynamic Knowledge
* Enterprise Use Cases
* Why RAG Became the Standard

---

# 2. Introduction to RAG (45 min)

### What is Retrieval-Augmented Generation

* Concept Overview
* RAG Architecture

### Core Components

* Documents / Knowledge Base
* Embeddings
* Vector Database
* Retrieval
* Prompt Augmentation

### RAG Pipeline

```
User Query
   ↓
Embedding
   ↓
Vector Search
   ↓
Retrieve Relevant Context
   ↓
LLM Generation
```

---

# 3. Designing a RAG System (45 min)

### Document Processing

* Chunking Strategies
* Metadata

### Embeddings

* What embeddings represent
* Choosing embedding models

### Vector Databases

* Similarity Search
* Indexing

### Retrieval Techniques

* Top-K retrieval
* Hybrid search
* Reranking (concept)

---

# 4. Hands-on: Build Your First RAG (2 hours)

Participants will build a **basic RAG chatbot**

### Step 1: Load Documents

* PDFs
* Web pages
* Text data

### Step 2: Chunk Documents

### Step 3: Generate Embeddings

### Step 4: Store in Vector Database

### Step 5: Implement Retrieval

### Step 6: Generate Answer with LLM

End Result

* Simple **knowledge chatbot**

---

# 5. Improving RAG Quality (1 hour)

Common Problems

* Irrelevant retrieval
* Context overload
* Hallucinations

Techniques

* Better chunking
* Query rewriting
* Reranking
* Context filtering

Evaluation

* Retrieval accuracy
* Answer quality

---

# 6. Advanced RAG Concepts (45 min)

### Agentic RAG

Agents that decide when and how to retrieve knowledge

### Agentic Design Patterns

* Planner → Executor
* Retrieval Planning

### Multi-Agent Systems

Different agents for:

* retrieval
* reasoning
* verification

---

# 7. Wrap-up + Q&A (15 min)

Key Takeaways

* When to use RAG
* RAG architecture
* How to build and improve it
* Future: agentic systems
