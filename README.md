# All-In Academy

All-In Academy is a professional, brand-safe rebuild of the original single-file poker trainer. It turns the concept into a full-stack Texas Hold'em training lab with a React + TypeScript frontend and a FastAPI backend.

## Why this version is more company-ready

- **React frontend:** reusable components, typed models, state-driven screens, and a Vite workflow.
- **FastAPI backend:** documented REST endpoints, Pydantic validation, CORS setup, and OpenAPI docs.
- **Server-side poker engine:** deck generation, betting actions, hand evaluation, opponent decisions, and coaching hints run through the API.
- **Professional brand:** no anime/IP references, making it safer to submit to companies or add to a portfolio.
- **Clear talking points:** you can discuss component design, API design, algorithms, validation, testing, and deployment.

## Project structure

```text
all_in_academy_fullstack/
  frontend/
    src/
      App.tsx
      components/
        CardView.tsx
        Coach.tsx
        Learn.tsx
        MetricCard.tsx
        Simulator.tsx
      lib/api.ts
      types.ts
      data.ts
      styles.css
  backend/
    app/
      main.py          # FastAPI routes
      poker_engine.py  # deck, betting flow, evaluator, bot logic
      coach.py         # coaching endpoint logic
      schemas.py       # Pydantic request/response models
    tests/
      test_poker_engine.py
```

## Run locally

### 1. Backend

```bash
cd backend
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
fastapi dev app/main.py
```

Backend: `http://localhost:8000`

API docs: `http://localhost:8000/docs`

### 2. Frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Frontend: `http://localhost:5173`

## API endpoints

- `GET /api/health`
- `POST /api/games`
- `GET /api/games/{game_id}`
- `POST /api/games/{game_id}/actions`
- `POST /api/coach`

## Portfolio description

> Built a full-stack poker education platform with a React + TypeScript frontend, FastAPI backend, playable Texas Hold'em simulator, server-side hand evaluation engine, opponent decision logic, and API-powered poker coach.

## Demo script for companies

1. Open the dashboard and explain the product goal.
2. Launch the simulator and walk through a hand.
3. Show how each player action calls the FastAPI backend.
4. Ask the coach, “What should I do?”
5. Open `/docs` to show the API contract.
6. Explain that the backend evaluates the best 5-card hand from up to 7 available cards.

## Next upgrades

- Add user accounts and saved training history.
- Add PostgreSQL for persistent hand histories.
- Add quiz mode and progress analytics.
- Add Docker production builds.
- Add an optional LLM provider behind the coach endpoint.
