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

## 04 - Pydantic model to structure output


### What I did
- Defined structured output using **Pydantic models**
- Used `Field()` to validate and describe data
- Forced the LLM to return structured data instead of raw text
- Converted LLM output into Python objects
- Transformed output into:
  - list of dictionaries
  - pandas DataFrame
- Exported results to:
  - `.csv`
  - `.md`
  - `.json`
- Loaded external text data from files for prompting

### What I learned
- LLM outputs can be **controlled and validated** using Pydantic
- Structured output makes data:
  - easier to process
  - reusable in pipelines
- `.model_dump()` converts models → dictionaries
- `.model_dump_json()` creates clean JSON output
- Encoding (`utf-8`) is important for handling special characters (å, ä, ö)
- LLM + structured schema = more reliable results

### Key Concepts
- **Unstructured vs Structured output**
- **Data validation with Pydantic**
- **Schema-driven LLM responses**
- **Data pipelines (LLM → DataFrame → file)**

### Experiments
- Simulated employee data with constraints (age, salary, role)
- Enforced schema with `Literal` and field limits
- Converted output to DataFrame and calculated statistics
- Extracted structured education data from raw text
- Saved structured results as JSON

### Insights
- Without structure → output is inconsistent and hard to use  
- With Pydantic → output becomes predictable and production-ready  
- LLMs can act like **data generators with schemas**
- This is a key step toward **real-world AI systems (MLOps)**