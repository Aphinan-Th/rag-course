# Workshop Setup Instructions
# 1-Day Workshop: Building RAG Systems

## Pre-requisites

- Python 3.10 or higher
- `uv` installed — [docs.astral.sh/uv](https://docs.astral.sh/uv/getting-started/installation/)
- A code editor (VS Code recommended)
- Basic Python knowledge

**API Key — choose one (or both):**

- **Google AI Studio** (default) — [aistudio.google.com](https://aistudio.google.com) → Get API Key
- **OpenRouter** — [openrouter.ai/keys](https://openrouter.ai/keys) → Create Key

---

## 1. Clone / Download Workshop Files

```bash
# All files should be in the rag-system/ folder
ls
# instructions.md  pyproject.toml  workshop.ipynb  sample_docs/
```

---

## 2. Create a Virtual Environment

```bash
uv venv
```

This creates a `.venv/` folder. Activate it:

```bash
# Mac / Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

---

## 3. Install Dependencies

```bash
uv sync
```

That's it — `uv` reads `pyproject.toml` and installs everything automatically.

---

## 4. Set Your API Key

### Option A — Google AI Studio (default workshop)

```bash
# Mac / Linux
export GOOGLE_API_KEY="AIza..."

# Windows (Command Prompt)
set GOOGLE_API_KEY=AIza...

# Windows (PowerShell)
$env:GOOGLE_API_KEY="AIza..."
```

### Option B — OpenRouter

```bash
# Mac / Linux
export OPENROUTER_API_KEY="sk-or-..."

# Windows (Command Prompt)
set OPENROUTER_API_KEY=sk-or-...

# Windows (PowerShell)
$env:OPENROUTER_API_KEY="sk-or-..."
```

Or create a `.env` file in the project root:

```
# Choose one (or both)
GOOGLE_API_KEY=AIza...
OPENROUTER_API_KEY=sk-or-...
```

---

## 5. Launch Jupyter Notebook

```bash
# Google AI Studio version (default)
uv run jupyter notebook workshop.ipynb

# OpenRouter version
uv run jupyter notebook workshop_openrouter.ipynb
```

---

## Workshop File Structure

```
rag-system/
├── instructions.md           ← You are here
├── pyproject.toml            ← Python dependencies (uv)
├── workshop.ipynb            ← Hands-on notebook (Google AI Studio)
├── workshop_openrouter.ipynb ← Hands-on notebook (OpenRouter)
└── sample_docs/
    ├── company_policy.txt
    ├── product_faq.txt
    └── employee_handbook.txt
```

---

## Models Used in This Workshop

### Google AI Studio (`workshop.ipynb`)

| Component       | Model                  | Cost (approx)         |
|-----------------|------------------------|-----------------------|
| Embeddings      | text-embedding-004     | Free tier available   |
| LLM             | gemini-2.0-flash       | Free tier available   |
| Vector Database | ChromaDB (local)       | Free                  |

The default workshop runs entirely within the **Google AI Studio free tier**.

### OpenRouter (`workshop_openrouter.ipynb`)

| Component       | Model                          | Cost (approx)       |
|-----------------|--------------------------------|---------------------|
| Embeddings      | openai/text-embedding-3-small  | Pay-per-use         |
| LLM             | openai/gpt-4o-mini             | Pay-per-use         |
| Vector Database | ChromaDB (local)               | Free                |

OpenRouter gives you access to many models — swap `LLM_MODEL` in the notebook to try others (e.g. `anthropic/claude-3-haiku`, `meta-llama/llama-3-8b-instruct`).

---

## What You Will Build

By the end of Section 4 (Hands-on), you will have a working chatbot that:

1. Loads documents from your `sample_docs/` folder
2. Chunks them into searchable pieces
3. Generates embeddings and stores them in a vector database
4. Retrieves relevant context when you ask a question
5. Generates accurate answers grounded in your documents

---

## Troubleshooting

**`ModuleNotFoundError`** — Make sure your virtual environment is activated and you ran `uv sync`.

**`google.auth.exceptions.DefaultCredentialsError`** — Your `GOOGLE_API_KEY` is missing or incorrect. Double-check the value.

**`chromadb` errors on Windows** — Try `uv add chromadb --upgrade`.

**`uv` not found** — Install it first: `curl -LsSf https://astral.sh/uv/install.sh | sh` (Mac/Linux) or see [docs.astral.sh/uv](https://docs.astral.sh/uv).

---

## After the Workshop

- Section 5 of the notebook covers techniques to improve your RAG system
- Section 6 introduces Agentic RAG patterns
- Recommended next steps are listed at the end of the notebook
