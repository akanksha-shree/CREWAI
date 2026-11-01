# CrewSphere AI — Architecture-backed CrewAI API

This folder exposes the required assignment contract while using the full CrewAI implementations in `../.. /backend` (relative to the project root). Keep the entire project folder when running this packaged version.

## API contract

`POST /agent1` through `POST /agent10` accept:

```json
{"input": "Your task description or source content"}
```

Each successful agent response returns `{"output": "..."}`. Agent 10 produces a draft that requires human review; use `POST /agent10/review` with `{"draft_id":"...","decision":"approved"}` or `{"draft_id":"...","decision":"revise","feedback":"..."}`.

## Run on Windows PowerShell

From the `submission/crewai` directory, with the full project folder extracted:

```powershell
python -m pip install -r requirements.txt
$env:GEMINI_API_KEY="YOUR_GEMINI_API_KEY"
python -m uvicorn app:app --reload --port 8000
```

The API also loads a project `.env` file when present. Do not commit `.env` or API keys. DuckDuckGo search does not require a search API key.

Open `http://127.0.0.1:8000/docs`.

## Architecture

See `ARCHITECTURE_ALIGNMENT.md` in the project root for the mapping of all ten modules to the supplied Crew/Flow diagrams, including the approval review step.

## Deployment

Deploy the complete project (not just this subfolder) as a Python web service. Build: `pip install -r requirements.txt`. Start: `uvicorn submission.crewai.app:app --host 0.0.0.0 --port $PORT` from the project root, or use the platform's equivalent working-directory configuration. Set `GEMINI_API_KEY` as a secret environment variable.
