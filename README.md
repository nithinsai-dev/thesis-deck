# ThesisDeck

An AI-powered equity research copilot that combines deterministic financial data with a multi-step agentic workflow to generate structured **Bull vs. Bear** investment theses.

Built as a personal full-stack + agentic AI project to speed up fundamental research without letting an LLM hallucinate financial numbers.

---

## How It Works

Instead of asking an LLM to recall stock prices or ratios from memory, **ThesisDeck** separates data fetching from reasoning:

1. **Data Agent (Deterministic Tools):** Fetches live price, valuation metrics (P/E, P/B, ROCE, Market Cap), and recent news headlines for any supported ticker (e.g., `SAIL.NS`, `NALCO.NS`).
2. **Analyst Agent:** Synthesizes the verified numbers and news into a structured Bull case and Bear case.
3. **Devil's Advocate Agent:** Stress-tests the Bull case by highlighting valuation risks, sector headwinds, and potential blind spots.
4. **Thesis Tracker:** Saves the generated report and your personal notes to a watchlist so you can review whether your original thesis played out.

---

## Tech Stack

* **Frontend:** React, TypeScript, Vite, Tailwind CSS
* **Backend:** FastAPI (Python) / Node.js
* **Agentic AI:** LangGraph / Tool-calling LLM workflow with live streaming (SSE)
* **Market Data:** `yfinance` + News API
* **Database:** PostgreSQL / Supabase

---

## Core Features (v1)

- [ ] Search any NSE/global stock ticker
- [ ] Real-time streaming of each agent's reasoning steps in the UI
- [ ] Verified financial metrics panel (no LLM math)
- [ ] Structured Bull vs. Bear + Risk breakdown
- [ ] Save & track investment theses in a personal watchlist

---

## Local Setup

```bash
# 1. Clone the repository
git clone [https://github.com/](https://github.com/)<your-username>/thesis-deck.git
cd thesis-deck

# 2. Configure environment variables
cp .env.example .env
# Add your LLM API key and database URL

# 3. Run the backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

# 4. Run the frontend
cd ../frontend
npm install
npm run dev
