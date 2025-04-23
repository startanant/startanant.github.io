
# 💹 Financial Modeling Prep (FMP) – Free Stock Market API

Access real-time and historical stock data, financial statements, and market indices with a JSON-based REST API.

---

## 🔗 Base URL

```
https://financialmodelingprep.com/api/v3/
```

---

## 🔐 Authentication

You’ll need a free API key.  
👉 [Get one here](https://financialmodelingprep.com/developer/docs/)

---

## ✅ Popular Endpoints (Free Tier)

### 📊 1. Get Real-Time Quote

**Endpoint:**

```
GET /quote/{symbol}
```

**Example:**

```
GET https://financialmodelingprep.com/api/v3/quote/AAPL?apikey=YOUR_API_KEY
```

**Sample Response:**

```json
[
  {
    "symbol": "AAPL",
    "price": 184.9,
    "changesPercentage": -0.54,
    "change": -1.0,
    "dayLow": 183.5,
    "dayHigh": 186.1,
    "volume": 55393000
  }
]
```

---

### 🧾 2. Company Profile

**Endpoint:**

```
GET /profile/{symbol}
```

**Example:**

```
GET https://financialmodelingprep.com/api/v3/profile/MSFT?apikey=YOUR_API_KEY
```

**Sample Response:**

```json
[
  {
    "symbol": "MSFT",
    "companyName": "Microsoft Corporation",
    "industry": "Software—Infrastructure",
    "ceo": "Satya Nadella",
    "description": "Microsoft develops, licenses, and supports software products...",
    "website": "https://www.microsoft.com"
  }
]
```

---

### 📈 3. Historical Price Data (Daily)

**Endpoint:**

```
GET /historical-price-full/{symbol}?serietype=line
```

**Example:**

```
GET https://financialmodelingprep.com/api/v3/historical-price-full/GOOGL?serietype=line&apikey=YOUR_API_KEY
```

**Sample Response:**

```json
{
  "symbol": "GOOGL",
  "historical": [
    { "date": "2025-04-15", "close": 2841.59 },
    { "date": "2025-04-14", "close": 2825.30 }
  ]
}
```

---

## 📋 Other Available Endpoints (Free Tier)

- `/stock-screener` – Filter stocks by market cap, price, etc.
- `/gainers` and `/losers` – Top market movers
- `/search` – Find companies by name or symbol

---

## ⚙️ Usage & Rate Limits

- **Free tier:** ~250 requests/day
- Higher tiers available for increased limits

---

## 🛠️ Docs & Tools

- [FMP API Documentation](https://financialmodelingprep.com/developer/docs)
- JSON format, easy for use with Python, JavaScript, or Postman

---
