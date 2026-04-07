```
LLMOps/
├── .venv
├── 03_llm_intro/
│    ├─llm_intro.ipynb     
├─   └── pic.jpg           
├── .env                     
├── .gitignore
├── .python-version
├── pyproject.toml
├── uv.lock
└── README.md 
```
# LLMOps Learning Journey

## 03 -  LLM intro with PydanticAI and OpenRouter

### Setup
- Created virtual environment using `uv`
- Added dependencies: `pydantic_ai`, `ipykernel`
- Configured API key from OpenRouter in `.env`

### What I did
- Created my first LLM agent using `pydantic_ai`
- Added a custom system prompt
- Ran prompts and printed responses
- Analyzed token usage and model metadata
- Experimented with temperature to control response style
- Added multimodal input (image + text)

### What I learned
- Difference between system prompt and user prompt
- How an LLM response is structured (output + metadata)
- Token usage includes input, output, and reasoning tokens
- Temperature affects creativity vs determinism
- LLMs can handle multiple input types (text + images)


### Experiments
- Asked the model for a joke
- Asked about weather (to see behavior with factual questions)
- Changed temperature to observe response differences
- Passed an image to the model and analyzed its response
- Tested prompts in different languages (English + Swedish)

### Insights
- The system prompt strongly affects tone and behavior
- Lower temperature → more deterministic responses
- Higher temperature → more creative responses
- Token usage is important for cost and performance
- LLM responses include useful debugging info (metadata)
- Multimodal models can interpret images and combine with text
