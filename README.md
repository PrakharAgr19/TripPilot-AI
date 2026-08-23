# ✈️ TripPilot AI — Intelligent Multi-Agent Travel Planning System

TripPilot AI is an open-source travel planning platform that uses multiple AI agents to transform a simple travel request into a complete travel experience. Instead of searching across different booking websites and manually organizing information, TripPilot AI coordinates specialized agents to research flights, discover accommodations, design personalized itineraries, and deliver everything in one structured response.

Built with LangGraph, LangChain, FastAPI, and Groq, the system demonstrates how agentic AI can solve complex, multi-step real-world tasks.

---

## Why TripPilot AI?

Planning a trip isn't just about booking flights—it's about balancing destinations, budgets, accommodations, activities, and schedules. Doing all of this manually often requires jumping between multiple websites and piecing everything together.

TripPilot AI automates this workflow by assigning each task to a dedicated AI agent. Every agent focuses on a specific responsibility while LangGraph manages the overall execution, allowing the system to generate organized and context-aware travel plans from a single user prompt.

---

## Key Features

- ✈️ Finds suitable flight options based on travel preferences
- 🏨 Researches and recommends hotels from live web sources
- 🗓️ Builds personalized day-by-day travel itineraries
- 🤖 Coordinates multiple AI agents using LangGraph
- ⚡ Generates fast responses using Groq LLMs
- 💾 Stores conversation history and workflow state with PostgreSQL
- 🌐 Exposes REST APIs through FastAPI with a lightweight web interface

---

## Tech Stack

- Python 3.10+
- FastAPI
- LangGraph
- LangChain
- Groq LLM
- PostgreSQL
- Tavily Search API
- AviationStack API
- HTML, CSS & JavaScript

---

## Project Structure

```text
.
├── app.py                # FastAPI application
├── backend.py            # Multi-agent LangGraph workflow
├── requirements.txt      # Project dependencies
├── static/               # Frontend assets
├── templates/            # HTML templates
└── tools/                # External API integrations
```

---

## Prerequisites

Before running the project, make sure you have:

- Python 3.10 or above
- PostgreSQL installed and running
- API keys for:
  - Groq
  - Tavily
  - AviationStack

---

## Environment Variables

Create a `.env` file in the project root.

```env
DATABASE_URL=postgresql://user:password@localhost:5432/travel_db
GROQ_API_KEY=your_groq_api_key
AVIATIONSTACK_API_KEY=your_aviationstack_api_key
TAVILY_API_KEY=your_tavily_api_key
DEFAULT_ORIGIN_IATA=DAC
```

---

## Installation

```bash
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

---

## Running the Application

Launch the FastAPI server.

```bash
python app.py
```

Open your browser:

```text
http://127.0.0.1:8000/
```

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | Verify server status |
| POST | `/api/travel` | Generate a travel plan |

Example request:

```bash
curl -X POST http://127.0.0.1:8000/api/travel \
  -H "Content-Type: application/json" \
  -d '{"message":"Plan a 3-day trip to Tokyo with a budget of $1200"}'
```

---

## System Workflow

The travel planning process is divided into multiple AI-powered stages:

1. **User Request** – Receives the travel requirements in natural language.
2. **Flight Agent** – Searches for suitable flight options.
3. **Hotel Agent** – Collects and evaluates accommodation choices.
4. **Itinerary Agent** – Creates a day-wise travel schedule based on user preferences.
5. **Response Agent** – Consolidates outputs from all agents into a polished travel plan.

Each agent communicates through a shared LangGraph state, allowing information to flow seamlessly across the workflow before producing the final response.

---

## Acknowledgments

TripPilot AI is designed as an end-to-end demonstration of agentic AI systems. It showcases how specialized AI agents, external APIs, and workflow orchestration can work together to automate complex travel planning while maintaining a modular and scalable architecture.



postgresql://prakhar:vwobVklNaYnpwcoI1b7rJ23zM554F3yL@dpg-da5e3o0jo6nc73ca02ig-a.ohio-postgres.render.com/agentmemory_6f3t