# MarketPulse 📈

An automated daily stock market briefing that pulls worldwide financial news, analyzes it using AI, and delivers an options-focused trading digest to your Discord every weekday morning before market open.

> **Disclaimer:** This tool is for informational purposes only. Nothing here is financial advice. Always do your own research before trading.

## What It Does

- Pulls the latest market news every weekday at 6am PST (before market opens)
- Aggregates from 5 major financial news sources worldwide
- Uses Google Gemini AI to generate an options-focused pre-market briefing
- Delivers the digest to Discord automatically — only on trading days (Mon–Fri)

## What You Get Every Morning

- **Market Sentiment** — overall direction for the day
- **Top Catalysts** — earnings, Fed events, economic data releases
- **Sectors to Watch** — where the momentum is
- **Stocks in Play** — individual names with news that could move prices
- **Risk Factors** — volatility warnings

## News Sources

| Source | Focus |
|--------|-------|
| Yahoo Finance | Broad market news |
| MarketWatch | Markets & economy |
| CNBC Top News | Breaking financial news |
| CNBC Markets | Market-specific coverage |
| Investing.com | Global markets & forex |

## Tech Stack

- **n8n** — workflow automation
- **Google Gemini** — AI analysis (free tier)
- **Discord Webhook** — delivery

## Setup

### Prerequisites
- [n8n](https://n8n.io) account
- [Google AI Studio](https://aistudio.google.com) account (free Gemini API key)
- Discord server with a webhook URL

### Steps

1. Import `market-news.json` into n8n
2. Add your Google Gemini API key to the Google Gemini node
3. Replace the Discord webhook URL in the Post to Discord node
4. Activate the workflow

The digest runs automatically every weekday at 6am PST (right before US market open at 9:30am ET).

## Related Projects

- [TechPulse](https://github.com/D1leonnn/techpulse) — Daily tech news digest
