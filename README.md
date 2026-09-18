# Koam Analytics

Independent quantitative research project. Santiago, Chile. One developer, self-funded, no external investment.

**Project site:** https://koamg1.github.io/koam-analytics/
**Contact:** wjesus19697106@gmail.com

---

## What this is

I research systematic trading strategies for index futures (DAX, US100) and DeFi liquidity pools. Every strategy depends on clean historical market data, and obtaining it has turned out to be the hardest part of the work.

Retail data feeds drop WebSocket connections during volatility spikes, which are exactly the periods a strategy has to be tested against, and those gaps cannot be reconstructed afterwards. Collectors have to run continuously and unattended, close to the venue.

Mine run on a single desktop machine on a residential connection. That machine holds 9.45 GB of collected market data across 3,023 datasets and five venues, and it is full.

## What exists today

Nine prototypes, developed between August and September 2026. File counts exclude dependencies and build artifacts.

| Repository | Focus | Python | Solidity | Files |
|---|---|---:|---:|---:|
| finance_project | Market data & strategy research | 476 | — | 3,664 |
| koamflashloan | Flash-loan execution contracts | 65 | 15 | 1,204 |
| HyperArb | Cross-venue arbitrage engine | 26 | — | 48 |
| koamflasharb | Flash arbitrage routing | 19 | 8 | 3,963 |
| KoamDepegHunter | Stablecoin depeg detection | 11 | — | 20 |
| LoopYield | Yield loop strategies | 7 | 6 | 21 |
| KoamObserver | Telemetry & monitoring | 5 | — | 13 |
| RobinArb | Spread scanner | 4 | — | 9 |
| Bot_lighter | Execution client (TypeScript) | — | — | 19 |

Roughly 620 Python modules and 29 Solidity contracts. None of it is in production — that is precisely the gap.

## The data bank

| Repository | Size on disk | Datasets | Files |
|---|---:|---:|---:|
| finance_project | 5.98 GB | 1,555 | 3,664 |
| Efinance_project_fondeo | 3.47 GB | 1,468 | 3,217 |
| **Total** | **9.45 GB** | **3,023** | **6,881** |

Sources: Binance, Bybit, OKX, Hyperliquid and MetaTrader 5 (through its Python API), in 1-minute, 1-hour and daily series, plus funding rates, spreads, contract specifications, and index and gold series. A dedicated data-quality layer checks every series for gaps and anomalies before it reaches a backtest.

## What is missing

Somewhere to run it. Collectors and execution workers need to sit close to the venues and stay up unattended, and the data bank needs storage that is not a desktop disk. The next data layer I want to collect is order-book depth, which I currently cannot store at all.

## Stack

Python, Solidity, TypeScript.

## A note on this repository

This repository holds the public description of the project. The strategy and execution code is kept private while the research is ongoing.
