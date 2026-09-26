# oneapi-lite

FastAPI gateway in front of an LLM with response caching

Built for my own use; public in case it helps someone.

## What it does

- POST /v1/chat with prompt/model/max_tokens
- SHA-256 keyed in-memory response cache
- Provider SDK plugs into one function
- Latency measured and returned per request

## Examples

```bash
curl localhost:8000/v1/chat \
  -H 'content-type: application/json' \
  -d '{"prompt": "hello", "model": "gpt-4o-mini"}'
```

## Install

```bash
pip install -r requirements.txt
uvicorn main:app --reload
```

## Project structure

```text
├── .github/
│   ├── workflows/
│   │   └── ci.yml
│   └── pull_request_template.md
├── docs/
│   ├── configuration.md
│   ├── development.md
│   ├── roadmap.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── main.py
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
```
