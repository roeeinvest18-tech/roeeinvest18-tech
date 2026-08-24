# Roee

Builder at the intersection of markets and software. I design systems that enforce discipline — in trading, in code, in how I structure my day.

---

## Featured Project — JARVIS

A production-grade personal intelligence system I designed and directed, built with Claude (Anthropic's AI coding agent) as my implementation partner. It runs live every weeknight.

**[Live dashboard](https://roeeinvest18-tech.github.io/jarvis-dashboard/)** · **Source code available on request**

[![Tests](https://github.com/roeeinvest18-tech/jarvis/actions/workflows/tests.yml/badge.svg)](https://github.com/roeeinvest18-tech/jarvis/actions/workflows/tests.yml)

### What it does

Every weekday night, JARVIS:

- Scans **576 US stocks** for zone-reclaim setups with composite scoring (6 dimensions, named constants, fully auditable)
- Reviews open positions against **10 risk limits** via the IBKR API
- Triages my inbox using ordered regex classification — ACTIONABLE / INFORMATIONAL / ROUTINE
- Competes all signals on a single **silence budget** of at most 3 items, then sends one Telegram message and goes quiet

A Progressive Web App shows the full detail. Personal data is encrypted client-side (AES-256-GCM, PBKDF2-SHA256 at 250,000 iterations) so the dashboard URL is public without leaking private information.

### The insight behind it

After closing 317 trades in IBKR and running FIFO analysis on the raw flex history, the win-rate split was unambiguous:

| Holding period | Win rate |
|---|---|
| Intraday | 6.1% |
| < 7 days | 12.9% |
| 7+ days | 58.4% |

JARVIS enforces the rules I already knew but wasn't consistently following.

### What this demonstrates

- **AI-assisted engineering** — directing a coding agent to build a production system is a distinct skill; every design decision was mine
- **Systems thinking** — silence budget, deny-by-default publish pipeline, dual-storage IndexedDB sync with tombstone deletions
- **Security awareness** — AES-256-GCM envelope encryption, gmail.readonly scope only, gitleaks on every push
- **$0 infrastructure** — GitHub Actions free tier, GitHub Pages, Railway hobby tier, yfinance, Reddit public API

### Stack

```
Python · GitHub Actions · Railway · Telegram Bot API
IBKR API · AES-256-GCM · SubtleCrypto · PWA · Service Worker
IndexedDB · Web Push (VAPID) · yfinance · Reddit API · Whisper (local)
```

---

**Contact:** roeeinvest18@gmail.com
