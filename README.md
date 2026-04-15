# LLMOps Learning Journey 🚀

This repository documents my journey learning how to build real-world AI systems with LLMs, from basic prompting to structured outputs, APIs, and evaluation.

---
## 📁 Project Overview

```
LLMOps/
├── .venv
├── 03_llm_intro/
│   ├── llm_intro.ipynb     
│   └── pic.jpg    
├── 04_pydanticai_structured_output/
│   ├── pydantic_pydantic_models.ipynb
│   ├── class_exercise.ipynb
│   ├── simulated_employees.csv
│   ├── simulated_employees.md
│   ├── education.json
│   └── data/
│       ├── mlops.txt
│       └── nackademin_contacts.txt
├── 06_pydantic_fastapi_chatbot/
│   ├── api.py
│   ├── chat_agent.py
│   ├── data_models.py
│   ├── constants.py
│   ├── frontend.py
│   └── chat.ipynb
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