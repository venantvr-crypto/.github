# venantvr.crypto

Analyse de marché crypto : collecte de données, signaux techniques et macro-économiques.

## Repos

| Repo | Stack | Description |
|------|-------|-------------|
| `Rust-Candles-Retriever` | Rust | Récupération offline de bougies Binance multi-timeframe + visualiseur TradingView |
| `Python.FED.Indicator` | Python | Analyse de sentiment des communiqués de la Federal Reserve (VADER, TextBlob) |
| `Python.Correlation.Capitalization` | Python | Corrélation RSI altcoins/BTC, filtrage par capitalisation |
| `Python.Crypto` | Python | Utilitaires crypto partagés |

## Pipeline

```
Collecte (Rust-Candles-Retriever / Binance API)
  |
  +-> Analyse technique (Python.Correlation.Capitalization / RSI multi-timeframe)
  |
  +-> Analyse macro (Python.FED.Indicator / NLP sur communiqués FED)
  |
  +-> Utilitaires partagés (Python.Crypto)
```

## Stack

- **Rust** pour la collecte haute performance (Binance REST API, SQLite, TradingView Lightweight Charts)
- **Python** pour l'analyse (pandas, numpy, NLTK, TextBlob, Flask)
- **SQLite** comme couche de stockage commune
- **Binance** et **CoinGecko** comme sources de données
