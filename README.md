# 📈 AI-Powered Stock Market Intelligence System
### Final Year Project | Data Analysis + ML + RAG + LLM + Agentic AI

---

## 🏗️ Project Architecture

```
┌────────────────────────────────────────────────────────────┐
│              STOCK MARKET AI INTELLIGENCE SYSTEM            │
│                                                            │
│  ┌──────────────┐   ┌──────────────┐   ┌───────────────┐  │
│  │  Notebook 1  │   │  Notebook 2  │   │  Notebook 3   │  │
│  │ Data Analysis│──▶│  ML Models   │──▶│  RAG + LLM    │  │
│  │    (EDA)     │   │              │   │               │  │
│  └──────────────┘   └──────────────┘   └───────────────┘  │
│         │                  │                   │           │
│         └──────────────────┴───────────────────┘           │
│                            │                               │
│                   ┌────────▼────────┐                      │
│                   │  Notebook 4     │                      │
│                   │  Agentic AI     │                      │
│                   │  (ReAct Agent)  │                      │
│                   └─────────────────┘                      │
└────────────────────────────────────────────────────────────┘
```

---

## 📚 Notebooks Overview

| # | Notebook | Component | Key Tech |
|---|----------|-----------|----------|
| 1 | `01_data_analysis.ipynb` | Data Collection + EDA | yfinance, Plotly, Seaborn |
| 2 | `02_ml_models.ipynb` | ML Classification + Backtesting | scikit-learn, XGBoost, LSTM |
| 3 | `03_rag_llm.ipynb` | RAG + LLM Q&A | LangChain, ChromaDB, Anthropic |
| 4 | `04_agentic_ai.ipynb` | Autonomous Agent | ReAct Loop, Custom Tools |

---

## ⚙️ Installation

```bash
pip install yfinance pandas numpy matplotlib seaborn plotly \
            scikit-learn xgboost langchain langchain-community \
            chromadb sentence-transformers anthropic joblib \
            requests beautifulsoup4 python-dotenv tensorflow
```

---

## 🔑 API Key Setup (for LLM in Notebook 3)

```python
# Option A: Environment variable
import os
os.environ['ANTHROPIC_API_KEY'] = 'sk-ant-...'

# Option B: .env file
# Create .env with: ANTHROPIC_API_KEY=sk-ant-...
```

> **Note:** Notebooks 1, 2, and 4 work fully **without any API key**.
> Notebook 3 falls back to demo mode if no key is set.

---

## 🚀 Run Order

```
1️⃣  01_data_analysis.ipynb   → generates stock_features.csv
2️⃣  02_ml_models.ipynb       → generates rf_model.pkl, ensemble_model.pkl, scaler.pkl
3️⃣  03_rag_llm.ipynb         → builds chroma_stock_db/ vector store
4️⃣  04_agentic_ai.ipynb      → runs autonomous agent (loads files from steps 1-3)
```

---

## 🧩 Components in Detail

### 📊 Data Analysis (Notebook 1)
- Downloads 5-year OHLCV data for 5 tech stocks via `yfinance`
- Engineers **17+ technical indicators**: RSI, MACD, Bollinger Bands, ATR, SMA/EMA
- Interactive candlestick dashboard with Plotly
- Correlation heatmaps, return distributions, VaR calculation
- Seasonal and annual return patterns

### 🤖 ML Models (Notebook 2)
- **Random Forest** classifier with feature importance
- **XGBoost** with early stopping and class balancing
- **LSTM** neural network for price regression (TensorFlow)
- **Ensemble Voting Classifier** (LR + RF + GBM)
- Time-series cross-validation (5-fold `TimeSeriesSplit`)
- Signal-based backtesting vs Buy & Hold benchmark

### 🔍 RAG + LLM (Notebook 3)
- Financial document knowledge base (earnings, macro, technical analysis)
- `RecursiveCharacterTextSplitter` for chunking
- `sentence-transformers/all-MiniLM-L6-v2` embeddings
- **ChromaDB** vector store with MMR retrieval
- Claude Haiku integration for grounded Q&A
- Retrieval quality evaluation (Precision@3)

### 🦾 Agentic AI (Notebook 4)
- **ReAct (Reasoning + Acting)** agent loop
- 5 custom tools: PriceTool, MLTool, RiskTool, PortfolioTool, ReportTool
- Multi-step autonomous planning
- Multi-turn conversational interface
- Agent execution trace visualization
- Comprehensive dashboard with matplotlib

---

## 📈 Key Results (Expected)

| Metric | Value |
|--------|-------|
| ML Model Accuracy | ~55–62% |
| ROC-AUC | ~0.57–0.65 |
| LSTM MAPE | ~2–5% |
| RAG Precision@3 | ~80% |
| Agent Steps | 5 per task |

---

## 🏛️ Project Report Structure

1. Introduction & Problem Statement
2. Literature Review (ML in finance, RAG, Agentic AI)
3. System Architecture
4. Data Collection & Feature Engineering
5. ML Model Development & Evaluation
6. RAG Pipeline Design
7. Agentic AI Framework
8. Results & Discussion
9. Conclusion & Future Work

---

## ⚠️ Disclaimer
This project is for **educational purposes only**. Do not use ML model signals for actual trading decisions.
## Copyright
Made by Rudra Abhishek
