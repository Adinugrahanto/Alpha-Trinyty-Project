# Alpha Trinity Trading System (EURUSD)

**Institutional-Grade EA System** combining:

* 📈 Smart Money Concepts (SMC)
* 🧠 Large Language Model (LLM) for real-time decision making
* 🐍 Python for data ingestion and AI communication
* 📊 MQL5 for precise MT5 trade execution

> Designed to dominate the London session using institutional flow, liquidity architecture, and advanced pattern recognition — not retail indicators.

---

## 📖 Table of Contents

1. [Overview](#alpha-trinity-trading-system-eurusd)
2. [System Architecture](#system-architecture)
3. [Core SMC Framework](#core-smc-framework)
4. [AI Decision Engine](#ai-decision-engine)
5. [Python Data Framework](#python-data-framework)
6. [MT5 Execution Engine](#mt5-execution-engine)
7. [Confidence Model](#confidence-model)
8. [JSON Protocols](#json-protocols)
9. [Implementation Roadmap](#implementation-roadmap)

---

## 🧠 System Architecture

```mermaid
graph TD
    A[MT5 (MQL5 EA)] -->|OHLC Feed| B[Python Collector]
    B -->|Context + Alpha Signals| C[LLM API]
    C -->|Signal (BUY/SELL/WAIT)| B
    C -->|Execution Plan| A
```

* **Session Focus:** London (08:00–12:00 GMT)
* **Execution Type:** Market order only, split TP logic
* **Data Latency:** Max 5 seconds between updates

---

## 📐 Core SMC Framework

### Market Structure Components

* **OB (Order Blocks)**
* **FVG (Fair Value Gaps)**
* **BOS/CHoCH**
* **Liquidity Sweeps**
* **Asia Range Liquidity Behavior**

### Institutional Logic

* Accumulation/Distribution Zones
* Liquidity Pool Mapping
* Volume Profile + DOM Snapshot
* Session Filtering (London/NY)

---

## 🧠 AI Decision Engine

### LLM Decision Logic

* Understands market context from Python JSON
* Uses compressed session history for reasoning
* Returns signal + confidence + monitoring protocol

### Confidence Gating System

* Trades only when score > `8.0/10`
* Scored on SMC strength, entry precision, intermarket bias, confirmation

### Output JSON Format

```json
{
  "bias": "BUY",
  "confidence": 8.8,
  "entry_zone": {"min": 1.2705, "max": 1.2708},
  "stop_loss": 1.2701,
  "take_profit": [1.2717, 1.2735],
  "risk_reward": 3.0,
  "monitoring_protocol": "B"
}
```

---

## 🐍 Python Data Framework

### Data Sources

* **Primary:** Polygon.io (OHLC)
* **Secondary:** Finnhub (DXY, Gold)
* **Backup:** AlphaVantage, FXCM

### Core Collection Cycle

* Protocol A: Every 15min (Surveillance Mode)
* Protocol B: 5min (Watch Mode)
* Protocol C: 1min (Execution Mode)

### Alpha Signal Examples

```json
{
  "volume_profile": {"poc": 1.2715, "vah": 1.2725},
  "asia_range": {"high": 1.2740, "low": 1.2700},
  "momentum": "bearish",
  "price": 1.2712
}
```

---

## 📊 MT5 Execution Engine (MQL5)

### Execution Parameters

* **Market Orders Only**
* **Position Split:**

  * TP1 @ RR 1:2 → move SL to BE
  * TP2 @ key structure or trail to RR 1:1 minimum
* **Max Spread:** 30 points (3 pips)
* **SL/TP Logic:** Buffer + confirmation

### Execution JSON Input

```json
{
  "symbol": "EURUSD",
  "risk_percent": 2.0,
  "entry_method": "market_order",
  "stop_loss": 1.2702,
  "tp1": 1.2717,
  "tp2": 1.2730,
  "split_position": true
}
```

---

## 🎯 Confidence Model

### Weighted Factors

* **SMC Structure**: OB quality, FVG alignment, BOS/CHoCH
* **Market Context**: Session timing, DXY alignment, volatility
* **Execution Quality**: Entry precision, RR ratio, volume spike
* **Technical Confluence**: TF alignment, divergence, volume

### Confidence Calculation Output

```json
{
  "total_confidence": 8.8,
  "action": "EXECUTE_BUY",
  "reasoning": ["Clean liquidity sweep", "OB + FVG confluence"]
}
```

---

## 🔌 JSON Protocols

### Protocol A – 15min

* Session context + structure check
* Liquidity pool monitoring

### Protocol B – 5min

* Zone proximity detection
* Momentum + volume analysis

### Protocol C – 1min

* Final confirmation
* Reversal pattern + DOM snapshot

---

## 🚀 Implementation Roadmap

### ✅ Phase 1: Python Collector

* [x] Setup Polygon API
* [ ] Collect OHLC + intermarket + DOM snapshot
* [ ] Output clean JSON for LLM

### ✅ Phase 2: LLM Bridge

* [ ] Build confidence engine
* [ ] Connect to LLM API (e.g., Claude/OpenAI)
* [ ] Test signal generation manually

### ✅ Phase 3: MT5 Integration

* [ ] Connect to HFM MT5
* [ ] Execute market orders from JSON
* [ ] Implement TP split, BE, RR trailing

### ✅ Phase 4: Testing

* [ ] Paper trade in demo
* [ ] Log decisions vs confidence
* [ ] Correlate confidence → win rate

---

## 🧪 Next Steps

* [ ] Finalize Python structure with minimal dependencies
* [ ] Confirm JSON I/O structure between components
* [ ] Begin backtesting London session setups
* [ ] Document confirmed alpha setups for LLM training

---

## 🔐 License

This project is under private development by Adi. Not for redistribution.

---

> For questions, implementation collaboration, or system design reviews — reach out in the consultation thread.
