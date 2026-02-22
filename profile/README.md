# venantvr.crypto

Analyse de marche crypto : collecte de donnees, signaux techniques et macro-economiques.

## Repos

| Repo | Stack | Description |
|------|-------|-------------|
| `Rust-Candles-Retriever` | Rust | Recuperation offline de bougies Binance multi-timeframe + visualiseur TradingView |
| `Python.FED.Indicator` | Python | Analyse de sentiment des communiques de la Federal Reserve (VADER, TextBlob) |
| `Python.Correlation.Capitalization` | Python | Correlation RSI altcoins/BTC, filtrage par capitalisation |
| `Python.Crypto` | Python | Utilitaires crypto partages |

## Pipeline

```
Collecte (Rust-Candles-Retriever / Binance API)
  |
  +-> Analyse technique (Python.Correlation.Capitalization / RSI multi-timeframe)
  |
  +-> Analyse macro (Python.FED.Indicator / NLP sur communiques FED)
  |
  +-> Utilitaires partages (Python.Crypto)
```

## Stack

- **Rust** pour la collecte haute performance (Binance REST API, SQLite, TradingView Lightweight Charts)
- **Python** pour l'analyse (pandas, numpy, NLTK, TextBlob, Flask)
- **SQLite** comme couche de stockage commune
- **Binance** et **CoinGecko** comme sources de donnees
