# 🤖 Barebone AI Clone — Community Edition

> **Free, local, private financial research dashboard** with Kronos-style Monte Carlo simulation & Taurus-style multi-agent AI debate. Runs 100% offline. No API keys. No subscriptions. Forever free.

![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg)
![Python](https://img.shields.io/badge/python-3.11+-green.svg)
![React](https://img.shields.io/badge/react-18+-61dafb.svg)
![Ollama](https://img.shields.io/badge/AI-Ollama%20%2B%20Llama%203.2-orange.svg)
![Cost](https://img.shields.io/badge/monthly%20cost-%240.00-brightgreen.svg)

---

## ✨ Features

| Feature | Description |
|:---|:---|
| 📈 **Monte Carlo Simulation** | 1,000 Geometric Brownian Motion paths → Bear / Base / Bull price targets with probability bar |
| 🤖 **Multi-Agent AI Debate** | Bull Agent vs Bear Agent → Risk Manager gives final BUY / HOLD / SELL verdict |
| 📊 **Technical Analysis** | RSI, MACD, Bollinger Bands, moving averages |
| 💰 **DCF Valuation** | Discounted Cash Flow intrinsic value calculator |
| 📰 **Sentiment Analysis** | News headline scoring & market mood |
| 🇮🇳 **India + US Markets** | NSE / BSE stocks + all US tickers via yfinance |
| 🔒 **100% Private** | All data stays on your laptop. Nothing sent to the cloud. |
| 🆓 **Zero Cost** | No OpenAI key. No subscriptions. Runs on Ollama + Llama 3.2 locally. |

---

## 🖥️ Screenshots

> Dashboard with Monte Carlo probability panel and multi-agent debate in action.

---

## 🚀 Quick Start (5 minutes)

### Prerequisites — install these once

| Tool | Download | Size |
|:---|:---|:---|
| Python 3.11+ | [python.org](https://python.org) | ~25 MB |
| Node.js 18+ | [nodejs.org](https://nodejs.org) | ~35 MB |
| Ollama | [ollama.com](https://ollama.com) | ~50 MB |

### Run in 3 terminals

**Terminal 1 — Backend**
```bash
cd backend
pip install -r requirements.txt
python app.py
```

**Terminal 2 — Frontend**
```bash
cd frontend
npm install
npm start
```

**Terminal 3 — AI (one-time 2GB download, then free forever)**
```bash
ollama run llama3.2
```

Open **http://localhost:3000** in your browser. Done! 🎉

---

## 🧠 How the AI Features Work

### Monte Carlo Simulation (Kronos-style)
Runs 1,000 simulated price paths using historical volatility (Geometric Brownian Motion). Shows:
- 🔴 **Bear Case** — 5th percentile outcome
- 🔵 **Base Case** — 50th percentile (median)
- 🟢 **Bull Case** — 95th percentile outcome
- **Probability Up %** — chance the stock finishes higher
- Time horizons: 7D / 14D / 30D / 60D / 90D

### Multi-Agent AI Debate (Taurus-style)
Three local LLM agents argue before giving you a verdict:
1. 🟢 **Bull Agent** — finds every reason to BUY
2. 🔴 **Bear Agent** — finds every risk and reason to AVOID
3. 🔵 **Risk Manager** — reads both arguments, gives balanced BUY / HOLD / SELL

All three agents run on **Ollama + Llama 3.2 locally** — zero API cost.

---

## 🔗 API Endpoints

| Method | Endpoint | Description |
|:---|:---|:---|
| GET | `/api/stock/{ticker}` | Stock fundamentals |
| GET | `/api/technical/{ticker}` | RSI, MACD, Bollinger Bands |
| GET | `/api/dcf/{ticker}` | DCF intrinsic value |
| GET | `/api/sentiment/{ticker}` | News sentiment score |
| GET | `/api/montecarlo/{ticker}` | **NEW** Monte Carlo simulation |
| GET | `/api/debate/{ticker}` | **NEW** Multi-agent Bull/Bear debate |

All endpoints accept `?market=US` or `?market=IN` for US/India markets.

---

## 💾 Tech Stack

```
Backend:   Python 3.11 + FastAPI + yfinance + numpy
Frontend:  React 18 + Recharts + Lucide Icons + TailwindCSS
AI:        Ollama + Llama 3.2 (3B) — runs on CPU, no GPU needed
Data:      Yahoo Finance (free) — no paid data feeds
```

**Total monthly cost: $0.00** 🎉

---

## 📁 Project Structure

```
barebone-ai-clone/
├── backend/
│   ├── app.py                    # FastAPI server + all API endpoints
│   ├── requirements.txt          # Python dependencies
│   └── analysis/
│       ├── technical.py          # RSI, MACD, Monte Carlo simulation
│       ├── dcf.py                # DCF valuation
│       ├── sentiment.py          # News sentiment
│       └── llm_wrapper.py        # Multi-agent debate logic
├── frontend/
│   ├── package.json
│   └── src/
│       ├── App.js
│       └── components/
│           ├── MonteCarloPanel.jsx   # NEW: probability simulation UI
│           ├── AgentDebatePanel.jsx  # NEW: bull/bear/risk debate UI
│           ├── PriceChart.jsx
│           ├── TechnicalMetrics.jsx
│           └── ...
└── README.md
```

---

## 🙏 Acknowledgements & Inspirations

This project was independently built by drawing conceptual inspiration from the following open-source projects. All original licenses are respected.

| Project | Author | License | Concept Borrowed |
|:---|:---|:---|:---|
| [TradingAgents](https://github.com/TauricResearch/TradingAgents) | Tauric Research | MIT | Multi-agent Bull/Bear/Risk debate architecture |
| [Kronos Quantitative Model](https://www.youtube.com/watch?v=ym2494IJ3V0) | Open Source Community | MIT | Monte Carlo probabilistic forecasting concepts |
| [Barebone.ai](https://barebone.ai) | Barebone Group Holdings | Proprietary | Financial dashboard UI/UX inspiration |

> ⚠️ **This project is NOT affiliated with, endorsed by, or connected to Barebone AI, Tauric Research, or any other mentioned project.** No proprietary source code was used. Concepts and algorithms are not copyrightable.

---

## ⚠️ Disclaimer

This is a community-built, open-source research tool for **educational and research purposes only**.

- ❌ NOT financial advice
- ❌ NOT affiliated with Barebone AI or any commercial product
- ✅ For learning, research, and personal use only
- Past performance does not guarantee future results

---

## 🤝 Contributing

Contributions are welcome! This is the beauty of open source — we build together.

1. Fork the repo
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Ideas for contributions
- [ ] Add more technical indicators (Fibonacci, ATR, Ichimoku)
- [ ] Add crypto support (BTC, ETH via yfinance)
- [ ] Add portfolio tracking across multiple tickers
- [ ] Add backtesting module
- [ ] Add email/Telegram alerts when Monte Carlo signals extreme moves
- [ ] Add support for European markets

---

## 📄 License

This project is licensed under the **GNU General Public License v3.0** — see the [LICENSE](LICENSE) file for details.

This means:
- ✅ Free to use, modify, and distribute
- ✅ Must keep it open source if you distribute it
- ✅ Cannot be taken proprietary — stays free forever

---

*Built with ❤️ by the community. If this helped you, give it a ⭐ so others can find it!*
