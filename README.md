crypto-signals/
├── backend/
│   ├── app/
│   │   ├── main.py            # FastAPI app, REST + WebSocket endpoints
│   │   ├── config.py          # env-based settings (pairs, timeframes, fees)
│   │   ├── data/
│   │   │   ├── binance_rest.py   # historical OHLCV, tickers
│   │   │   ├── binance_ws.py     # kline stream, reconnect, stale detection
│   │   │   └── store.py          # SQLite via SQLAlchemy
│   │   ├── indicators/        # EMA, RSI, MACD, BB, ATR, volume, S/R, patterns
│   │   ├── signals/
│   │   │   ├── rules.py       # documented rule set, NO TRADE logic
│   │   │   └── engine.py      # runs rules, attaches freshness + invalidation
│   │   ├── backtest/
│   │   │   ├── engine.py      # chronological train/validation/test, fees, slippage
│   │   │   └── binary.py      # fixed payout, expiry, tie handling
│   │   ├── paper/             # virtual account, positions, trade log
│   │   └── api/               # routes, rate limiting, validation
│   ├── tests/                 # indicator + signal + backtest unit tests
│   ├── requirements.txt
│   └── .env.example
├── frontend/                  # React + TypeScript + Tailwind + Lightweight Charts
│   └── src/ (components: PriceCards, Chart, IndicatorPanel, SignalTable, PaperTrading, StatusBar)
└── docs/ (SETUP.md, BACKTESTING.md, TROUBLESHOOTING.md)
