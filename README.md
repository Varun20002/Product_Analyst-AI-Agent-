# AI Product Analyst

AI-powered insights for Product Managers & Growth Teams

## Overview
AI Product Analyst is a Streamlit app that coordinates multiple specialized agents to generate actionable launch intelligence:
- Competitor Analysis
- Market Sentiment
- Launch Metrics

It runs on Gemini (Gemini 2.0 Flash Lite) via Agno and uses Firecrawl for web search/crawling.

## What you get
- Evidence-based bullets and structured Markdown reports
- Clear sections, call-outs, and tables (where relevant)
- Optional web search/crawling via Firecrawl

## Requirements
- Python 3.10+
- API keys:
  - GEMINI_API_KEY (or GOOGLE_API_KEY)
  - FIRECRAWL_API_KEY

## Quick start
```bash
# 1) Create & activate a virtual environment
python3 -m venv venv
source venv/bin/activate

# 2) Install dependencies
pip install -r requirements.txt

# 3) Run the app
streamlit run product_launch_intelligence_agent.py
```
Then open the local URL shown in your terminal (e.g., http://localhost:8501).

## Configuration
You can paste keys in the app sidebar, or export them as environment variables before launching:

```bash
export GEMINI_API_KEY=your_gemini_key
export FIRECRAWL_API_KEY=your_firecrawl_key
```
Notes:
- The app will mirror `GEMINI_API_KEY` to `GOOGLE_API_KEY` automatically for SDK compatibility.
- Firecrawl is required for search/crawl features. Without it, the app still runs but won’t fetch live sources.

## Default Model
- Gemini model: `gemini-2.0-flash-lite`

You can change the model by editing the `Gemini(id=...)` declarations in `product_launch_intelligence_agent.py`.

## Usage
1. Enter your API keys in the sidebar (Gemini + Firecrawl)
2. Enter a company name
3. Choose an analysis tab and click the Analyze button
   - 🔍 Competitor Analysis
   - 💬 Market Sentiment
   - 📈 Launch Metrics

### Keyboard shortcuts (when a company is set)
- J: Competitor analysis
- K: Market sentiment
- L: Launch metrics

## Project structure (repo)
- `product_launch_intelligence_agent.py` — Streamlit app
- `requirements.txt` — Python dependencies
- `README.md` — This guide

## Troubleshooting
- Missing key error (e.g., `GOOGLE_API_KEY not set`):
  - Ensure you’ve provided `GEMINI_API_KEY` in the sidebar or exported it before launch
- Rate limits (429 RESOURCE_EXHAUSTED):
  - Free tier quotas are limited; slow down requests or upgrade your quota
  - Using `gemini-2.0-flash-lite` helps reduce cost and limits
- Firecrawl tool errors:
  - Ensure your `FIRECRAWL_API_KEY` is valid
  - If issues persist, re-run after a few minutes; Firecrawl rate limits may apply
- Better performance (optional):
  - `xcode-select --install` (macOS) and `pip install watchdog` to improve Streamlit file watching

## License
Proprietary (update if you intend to open-source).
