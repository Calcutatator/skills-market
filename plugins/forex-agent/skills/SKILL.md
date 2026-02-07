---
name: forex-agent
description: |
  Builds a real-time currency exchange rate agent using Frankfurter/ECB API with x402 payments.
  Use when creating forex trading tools, currency converter agents, or international finance data feeds.
---

# Forex Agent

Real-time currency exchange rates from the European Central Bank via Frankfurter. 6 endpoints (1 free + 5 paid).

## Live

- **URL:** https://forex-agent-production.up.railway.app
- **GitHub:** https://github.com/Calcutatator/forex-agent

## API

**Source:** Frankfurter (European Central Bank)  
**Base URL:** `https://api.frankfurter.dev/v1`  
**Auth:** None required

## Endpoints

| Key | Price | Description |
|:----|:------|:------------|
| `overview` | Free | USD rates for EUR, GBP, JPY, CAD, CHF |
| `convert` | $0.001 | Convert amount between any two currencies |
| `history` | $0.002 | Historical rates for a date range |
| `currencies` | $0.001 | All 30+ supported currencies with rates |
| `volatility` | $0.003 | Min/max/spread/volatility for a pair |
| `report` | $0.005 | Comprehensive currency market report |

## Key API Endpoints

```
/latest?base=USD&to=EUR,GBP,JPY          # Current rates
/latest?amount=100&from=USD&to=EUR        # Convert
/2026-01-01..2026-01-31?base=USD&to=EUR   # Date range
/currencies                                # All currencies
```

## Stack

Bun + Hono + `@lucid-agents/core` + `@lucid-agents/payments` + Zod v4
