# StockRAGBot

A personal Retrieval-Augmented Generation (RAG) chatbot for stock market queries. It fetches real-time stock data, latest news, quarterly earnings, dividends, stock splits, and other corporate actions using APIs like yfinance and Finnhub. Supports global (e.g., AAPL, TSLA) and Indian stocks (e.g., RELIANCE.NS, TCS.NS). Built with LangChain, Hugging Face transformers, and a local LLM (Phi-2) for privacy and no external API quotas on generation.

## Features
- **Real-Time Data**: Current prices, changes, market cap, PE ratios via yfinance.
- **News & Corporate Actions**: Latest news, earnings, dividends, splits via Finnhub API.
- **RAG Integration**: Contextual responses using vector search (FAISS) on static docs and dynamic API data.
- **Ticker Detection**: Auto-detects stock symbols in queries (e.g., "What's the latest on TSLA?").
- **Local LLM**: Uses microsoft/phi-2 for generation—no OpenAI dependency.
- **Extensible**: Easy to add more stocks, APIs, or features like sentiment analysis.

## Requirements
- Python 3.10+
- Dependencies: Listed in `requirements.txt` (install with `pip install -r requirements.txt`).
  - Key libs: yfinance, finnhub-python, langchain, transformers, torch, faiss-cpu, sentence-transformers, etc.
- Finnhub API Key: Sign up at [finnhub.io](https://finnhub.io) for free tier (60 calls/min).

## Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/monu1086/StockRAGBot.git
   cd StockRAGBot
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Set environment variables:
   - Export your Finnhub API key
   ```
   export FINNHUB_API_KEY='your_finnhub_api_key_here'
   ```
## Usage Examples
- Basic: "Current price of TCS.NS?"
- News: "Latest updates for AMZN?"
- Earnings: "Latest quarterly results for INFY.NS?"
- Corporate Actions: "Dividends for HDFCBANK.NS?"
- General: "Tell me about Tesla Inc."
  The bot detects tickers automatically and fetches fresh data. If no ticker is found, it prompts for one.
## Limitations
- Free API tiers have rate limits (e.g., Finnhub: 60/min; yfinance: unofficial, may throttle).
- Local LLM (Phi-2) is lightweight; responses may be less sophisticated than GPT—upgrade to larger models like Mistral-7B if needed (requires more RAM/GPU).
- No internet in LLM; all generation is local.
- Expand static documents in code for more stocks.
## Contributing
Fork the repo, make changes, and submit a pull request. For issues, open a GitHub issue.
## Acknowledgments
- Built with inspiration from LangChain and Hugging Face.
- APIs: yfinance, Finnhub.
  
