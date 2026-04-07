```
LLMOps/
├── .venv
├── 03_llm_intro/
│   └──llm_intro.ipynb                 
├── .env                     
├── .gitignore
├── .python-version
├── pyproject.toml
├── uv.lock
└── README.md 
```
# LLMOps Learning Journey

## 03 - LLM Intro

### What I did
- Created my first LLM agent using `pydantic_ai`
- Added a custom system prompt
- Ran prompts and printed responses

### What I learned
- Difference between system prompt and user prompt
- How an LLM response is structured
- That responses include metadata (tokens, model, provider)

### Experiments
- Asked the model for a joke
- Asked about weather (to see behavior with factual questions)

### Insights
- The system prompt strongly affects tone and behavior
- The model returns more than just text (important for debugging)