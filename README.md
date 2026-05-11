# Daily Market Pulse

An automated n8n workflow that runs every weekday at 6am PST, pulls the latest stock market news from 9 sources, filters and deduplicates it, then uses Google Gemini AI to generate a pre-market briefing delivered straight to Discord — built specifically for options traders.

## How It Works

```
Scheduled Trigger (6am PST, Mon–Fri)
        ↓
9 RSS Feeds pulled in parallel
        ↓
Chained Merge Nodes (combines all feeds)
        ↓
Filter & Deduplicate (last 24h only, no repeated stories)
        ↓
Sort by Date → Top 20 Articles
        ↓
Format for AI
        ↓
Google Gemini 2.0 Flash (AI Summary)
        ↓
Discord Webhook → Market Pulse Bot
```

## News Sources

| Source | Coverage |
|--------|----------|
| Yahoo Finance | General market news |
| Investing.com | Global markets & analysis |
| Motley Fool | Stock picks & investing strategy |
| CNBC | Breaking financial news |
| MarketWatch | Market data & commentary |
| Reuters | Business & world news |
| Forbes | Business & economy |
| Benzinga | Options-focused market news |
| Nasdaq | Nasdaq original content |

## Discord Output Format

The bot posts a structured briefing every morning:

- **Market Sentiment** — bullish/bearish/neutral with reasoning
- **Top Catalysts Today** — earnings, Fed decisions, economic data
- **Sectors to Watch** — what's moving and why
- **Stocks in Play** — 2–3 tickers ideal for options plays
- **Risk Factors** — potential volatility surprises

## Tech Stack

- **n8n** — workflow automation
- **Google Gemini 2.0 Flash** — AI summarization
- **Discord Webhook** — delivery

## Setup

1. Import `workflow.json` into n8n via **Import from JSON**
2. Go to **Credentials** → add a **Google Gemini** API key
   - Get a free key at [aistudio.google.com](https://aistudio.google.com)
3. Link the credential to the **Google Gemini** node
4. Replace the Discord webhook URL in the **Post to Discord** node with your own
5. Toggle the workflow to **Active**

## Schedule

Runs Monday–Friday at 6am PST (`0 13 * * 1-5` UTC)

---

*Not financial advice. Do your own research.*