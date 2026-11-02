# CrewAI — Agent API

A collection of 10 AI agents built using CrewAI and FastAPI. Each agent is exposed through a REST API endpoint and accepts a JSON input.

## Live Deployment

- **Backend URL:** https://crewai-bpy1.onrender.com
- **API Documentation (Swagger):** https://crewai-bpy1.onrender.com/docs
- **GitHub Repository:** https://github.com/akanksha-shree/CREWAI

## Available Agents

| Endpoint | Agent | Function |
|---|---|---|
| `POST /agent1` | Blog Post Generation | Generates blog posts |
| `POST /agent2` | Competitor Analysis | Analyses competitors |
| `POST /agent3` | Meeting Notes | Processes meeting notes |
| `POST /agent4` | Data Report | Generates data reports |
| `POST /agent5` | Customer Support | Handles customer support queries |
| `POST /agent6` | Resume Screening | Screens resumes |
| `POST /agent7` | Bug Triage | Analyses and classifies bugs |
| `POST /agent8` | Content Repurposing | Repurposes existing content |
| `POST /agent9` | Lead Qualification | Qualifies potential leads |
| `POST /agent10` | Approval Report | Creates approval reports |

## API Request and Response Format

All ten agent endpoints accept a POST request with the following JSON structure:

**Request:**

```json
{
  "input": "Your task or instructions here"
}
```

**Response:**

```json
{
  "output": "Generated result from the agent"
}
```

## Approval Report Review

The approval workflow also provides a review endpoint:

`POST /agent10/review`

This endpoint handles the review of approval reports.

## Technology Stack

- Python
- CrewAI
- FastAPI
- Uvicorn
- Google Gemini API

## Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/akanksha-shree/CREWAI.git
cd CREWAI
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the API key

Set your Gemini API key as an environment variable named `GEMINI_API_KEY`.

Windows PowerShell:

```powershell
$env:GEMINI_API_KEY="your_gemini_api_key"
```

### 5. Start the server

```bash
uvicorn app:app --reload
```

The API will be available at:

`http://127.0.0.1:8000`

Open Swagger documentation:

`http://127.0.0.1:8000/docs`

## Deployment

The application is deployed as a backend service on Render.

- **Build Command:**

```bash
pip install -r requirements.txt
```

- **Start Command:**

```bash
uvicorn app:app --host 0.0.0.0 --port $PORT
```

Configure the following environment variables in Render:

- `GEMINI_API_KEY`
- `PYTHON_VERSION` = `3.13.5`

## API Testing

The endpoints can be tested using Postman or the Swagger UI documentation.

For each agent, send a POST request with the required JSON input and verify that the response contains an `output` field.

---

**Project:** CrewAI Agent API  
**Framework:** CrewAI + FastAPI
