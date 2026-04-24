# LLMOps Learning Journey 🚀

This repository documents my journey learning how to build real-world AI systems with LLMs, from basic prompting to structured outputs, APIs, and evaluation.

---
## 📁 Project Overview

```
LLMOps/
├── .venv
├── Code_alongs/
│ ├── 03_llm_intro/
│ │  ├── llm_intro.ipynb
│ │  └── pic.jpg
│ ├── 04_pydanticai_structured_output/
│ │  ├── pydantic_pydantic_models.ipynb
│ │  ├── class_exercise.ipynb
│ │  ├── simulated_employees.csv
│ │  ├── simulated_employees.md
│ │  ├── education.json
│ │  └── data/
│ ├── 06_pydantic_fastapi_chatbot/
│ │  ├── api.py
│ │  ├── chat_agent.py
│ │  ├── data_models.py
│ │  ├── constants.py
│ │  ├── frontend.py
│ │  └── chat_eda.ipynb
│ ├── 07_mlflow_llm_judge/
│ │ ├── data/
│ │ │ └── customer_service_emails.json
│ │ ├── constants.py
│ │ ├── data_cleaning.ipynb
│ │ ├── email_extractor.ipynb
│ │ ├── emails_cleaned.json
│ │ ├── mlflow.db
│ │ └── prompt_creations.ipynb
│   └── 09_lancedb/
│       ├── __pycache__/
│       ├── knowledge_base/
│       │   ├── animals_text.lance/
│       │   └── jokes.lance/
│       ├── .env
│       ├── animals_text_embeddings.json
│       ├── constants.py
│       ├── jokes.json
│       └── lancedb_basics.ipynb
│
├── .env
├── animals_text_embeddings.json
├── constants.py
├── jokes.json
└── lancedb_basics.ipynb
├── Exercises/
│    └── Exercise_0/
│         ├── data/
│         ├── Exercise_0.md
│         └── Exercise0.ipynb
├── .env
├── .gitignore
├── .python-version
├── pyproject.toml
├── uv.lock
└── README.md
```
# LLMOps Learning Journey

# 03 - LLM Intro (PydanticAI + OpenRouter)

### 🛠️ What I did
- Built my first LLM agent using `pydantic_ai`
- Used system prompts to control behavior
- Tested different prompts and model settings
- Experimented with temperature and multimodal input

### 📚 What I learned
- Difference between **system prompt vs user prompt**
- How LLM responses include metadata (tokens, etc.)
- Temperature controls creativity vs determinism
- LLMs can process text + images

### 💡 Insight
This step helped me understand how LLMs behave before adding structure or complexity.
---


# 04 - Structured Output with Pydantic

### 🛠️ What I did
- Defined structured schemas using **Pydantic**
- Forced LLM to return structured data
- Converted outputs into:
  - Python objects
  - DataFrames
  - JSON / CSV / Markdown

### 📚 What I learned
- Structured output = predictable + usable data
- `.model_dump()` → Python dict
- `.model_dump_json()` → JSON
- Validation improves reliability

### 💡 Insight
LLMs become much more useful when treated like **data generators with schemas**.

---

# 06 - FastAPI Chatbot

### 🛠️ What I did
- Built an API using **FastAPI**
- Created a chat agent with memory
- Used Pydantic models for validation
- Connected a Streamlit frontend

### 📚 What I learned
- How to build an LLM-powered API
- How frontend ↔ backend communication works
- Importance of structured input/output
- Managing conversation state

### 💡 Insight
Wrapping LLMs in APIs makes them usable in real applications.

---

# 07 - MLflow + LLM Judge 🧪

### 🛠️ What I did
- Cleaned and structured email dataset for evaluation
- Built an email extractor using Pydantic + LLM
- Created and versioned prompts using MLflow
- Loaded prompts dynamically into the agent
- Generated model outputs and stored them in a dataset
- Evaluated results using MLflow (`Correctness`, `Summarization`)

### ▶️ Run MLflow UI
```bash
uv run mlflow ui --port 5001
```

### 📚 What I learned
- Prompts can be versioned and reused with MLflow
- LLM outputs need to be structured for evaluation
- Evaluation requires:
  - inputs
  - expected outputs
  - model outputs
- MLflow helps track experiments and results

### 💡 Insight
Building LLM systems is not just about prompting — it also requires evaluation, tracking, and iteration.

---

# 08 - mlflow + fastapi + pydanticai

The full project implementation can be found here:
👉 [08_mlflow_fastapi_pydanticai](https://github.com/LAjoyan/FastAPI_LLMops_demo)

# 09 - LanceDB + Embeddings 🔍

## 🛠️ What I did
- Set up a local LanceDB knowledge base
- Created tables to store text + vector embeddings
- Loaded dataset from JSON files (animals, jokes)
- Inserted and updated data in tables
- Used schema with `LanceModel` for structured data
- Generated embeddings using LanceDB Embeddings API (Cohere)
- Stored embeddings automatically in the database
- Performed vector similarity search using:
  - manual query vectors
  - natural language queries

---

## 📚 What I learned
- Text must be converted into vectors (embeddings) to enable semantic search
- LanceDB stores data as `.lance` tables (not normal files)
- Embedding models automatically generate vectors (no need to create manually)
- Schema (`LanceModel`) helps structure and validate data
- Vector search finds similar meaning, not exact matches
- You can search using:
  - vectors
  - or plain text (converted internally to vectors)

---

## ⚠️ Notes
- Calling `.add()` multiple times appends data (does not overwrite)
- Re-running notebook cells can create duplicate entries
- LanceDB automatically versions tables after each write

---

## 💡 Insight
Building AI systems is not just storing data, it’s about:

- representing meaning with embeddings
- retrieving relevant information efficiently
- enabling semantic search (foundation for RAG systems)

👉 This is the core building block for:

- chatbots
- document search
- AI assistants