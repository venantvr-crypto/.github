# venantvr.crypto

Analyse de marché crypto : collecte haute performance de données OHLCV, signaux techniques multi-timeframe et analyse macro-économique par NLP.

## Repos

### Collecte de données

[![Rust-Candles-Retriever](https://img.shields.io/badge/Rust--Candles--Retriever-B7410E?style=for-the-badge&logo=rust&logoColor=white)](https://github.com/venantvr-crypto/Rust-Candles-Retriever) <sup>public</sup>
*Rust / Actix-Web* — Récupérateur de chandeliers Binance multi-timeframe (5m → 3d) avec stockage SQLite, interpolation automatique des gaps, mode reprise intelligent et visualiseur web interactif TradingView Lightweight Charts avec zoom adaptatif. Backend API Actix-Web, binaire optimisé (LTO).

[![Python.Crypto](https://img.shields.io/badge/Python.Crypto-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/venantvr-crypto/Python.Crypto) <sup>privé</sup>
*Python / Flask* — Agrégateur de données DEX (Uniswap V2/V3) : collecte CoinGecko, requêtes GraphQL TheGraph, appels on-chain Web3/Geth, résolution de routeurs et listes IPNS. API REST Flask avec mise en cache.

### Analyse

[![Python.Correlation.Capitalization](https://img.shields.io/badge/Python.Correlation.Capitalization-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/venantvr-crypto/Python.Correlation.Capitalization) <sup>public</sup>
*Python / ccxt* — Identification d'altcoins à faible capitalisation dont le RSI présente une forte corrélation de Pearson avec le Bitcoin, sur plusieurs unités de temps (1h, 4h, 1d). Architecture événementielle multi-threadée avec agents spécialisés (DataFetcher, RSICalculator, DisplayAgent), données via ccxt + CoinGecko, persistance SQLite.

[![Python.FED.Indicator](https://img.shields.io/badge/Python.FED.Indicator-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/venantvr-crypto/Python.FED.Indicator) <sup>public</sup>
*Python / Flask* — Analyse de sentiment des communiqués de la Réserve fédérale (FED) via trois moteurs NLP : VADER (NLTK), TextBlob document-level et TextBlob phrase-par-phrase. Interface web Flask + Bootstrap.

## Pipeline

```mermaid
graph LR
    subgraph Collecte
        A[Rust-Candles-Retriever<br/><i>Binance · multi-timeframe · gap-filling</i>] -->|OHLCV| DB[(SQLite)]
        B[Python.Crypto<br/><i>CoinGecko · TheGraph · Web3</i>] -->|DEX data| API[API REST]
    end
    subgraph Analyse
        DB --> C[Python.Correlation.Capitalization<br/><i>RSI · Pearson · ccxt</i>]
        API --> D[Python.FED.Indicator<br/><i>VADER · TextBlob · NLP</i>]
    end
```

## Stack

[![Stack](https://skillicons.dev/icons?i=python,solidity,docker,linux,git&theme=dark)](https://skillicons.dev)


- **Rust** (Actix-Web, rusqlite, binance-rs, tokio) pour la collecte haute performance
- **Python** (pandas, numpy, ccxt, Flask, NLTK, TextBlob, Web3.py) pour l'analyse
- **SQLite** comme couche de stockage commune
- **TradingView Lightweight Charts** pour la visualisation
- **Binance**, **CoinGecko** et **TheGraph** comme sources de données
