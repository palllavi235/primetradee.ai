# Trader Performance vs Market Sentiment (Fear–Greed Analysis)

This repository contains my submission for the **Data Science Intern – Round‑0 Assignment** at **Primetrade.ai**. The project analyzes how **market sentiment (Fear / Greed)** influences **trader performance and behavior** on the Hyperliquid trading platform, and proposes actionable strategy insights based on data.

---

## 📌 Objective

The goal of this analysis is to:

* Understand how trader **performance** (PnL, win rate, drawdown proxy) varies across market sentiment regimes
* Study changes in **trader behavior** (trade frequency, trade size, long/short bias)
* Identify meaningful **trader segments** (Frequent vs Infrequent)
* Derive **actionable trading rules of thumb** informed by data

---

## 📂 Datasets Used

### 1️⃣ Bitcoin Market Sentiment (Fear & Greed Index)

* **Columns:** `date`, `classification`
* **Values:** Extreme Fear, Fear, Neutral, Greed, Extreme Greed
* Used as a proxy for overall market psychology

### 2️⃣ Hyperliquid Historical Trader Data

* **Key columns:**

  * `account` – trader identifier
  * `timestamp` – execution time
  * `side` – BUY / SELL
  * `size_usd` – trade size
  * `closed_pnl` – realized profit or loss

Both datasets were aligned at a **daily level** and merged on date.

---

## 🧹 Data Preparation

* Converted timestamps to daily granularity
* Removed irrelevant columns and handled missing values
* Merged sentiment data with trade data by date
* Built **trader‑day level metrics**, where each row represents:

  > one trader × one day × one sentiment regime

---

## 📊 Key Metrics Created

For each trader‑day:

* **Daily PnL:** sum of all closed profits/losses
* **Win Rate:** fraction of profitable trades
* **Trades per Day:** trading frequency
* **Average Trade Size:** proxy for risk taken
* **Long Ratio:** proportion of BUY trades (directional bias)

---

## 📈 Analysis Performed

### 1️⃣ Performance vs Sentiment

* Compared **average daily PnL**, **win rate**, and **drawdown proxy** across sentiment regimes
* Observed that **Fear and Extreme Greed** periods show higher profitability but also higher risk

### 2️⃣ Behavior vs Sentiment

* Trade frequency increases sharply during **Fear**
* Average trade size is largest during **Fear**, indicating aggressive risk‑taking
* Long bias is higher during Fear, suggesting "buy‑the‑dip" behavior

### 3️⃣ Trader Segmentation

Traders were segmented into:

* **Frequent traders:** above‑median trading activity
* **Infrequent traders:** below‑median activity

Frequent traders consistently outperform infrequent traders, especially during Fear periods.

---

## 📊 Visualizations

The analysis includes the following core charts:

1. **Trading Activity vs Market Sentiment**
2. **Average Win Rate vs Market Sentiment**
3. **Frequent vs Infrequent Traders by Sentiment**

All charts were generated using Python (pandas + matplotlib) and are included as screenshots / images.

---

## 🔍 Key Insights

1. **Profitability is driven more by volatility than optimism** — Fear periods offer strong opportunities for skilled traders.
2. **Fear triggers overtrading and larger position sizes**, increasing both upside and downside risk.
3. **Frequent traders adapt better to sentiment extremes** and significantly outperform infrequent traders.

---

## 🎯 Strategy Recommendations (Rules of Thumb)

### ✅ Strategy 1: Risk Control During Fear

> During Fear periods, reduce position sizes and restrict aggressive long exposure for infrequent traders.

**Rationale:** Fear leads to overtrading and large positions, which can amplify losses for less experienced traders.

---

### ✅ Strategy 2: Selective Participation During Greed

> During Greed periods, allow higher participation only for historically frequent and consistent traders.

**Rationale:** Greed periods show lower win rates and meaningful drawdowns; experienced traders handle these conditions better.

---

## 🛠 Tools & Technologies

* **Python:** pandas, matplotlib
* **SQL (MySQL):** data aggregation and validation
* **Jupyter / VS Code:** analysis environment
* **PowerPoint:** final presentation of insights

---

## 📁 Repository Structure

```
├── data/                 # Raw datasets (if shared)
├── notebook.ipynb        # Full analysis notebook
├── images/               # Generated charts & screenshots
├── Trader_Performance_vs_Market_Sentiment.pptx
├── README.md             # This file
```

---

## 🧠 Conclusion

Market sentiment has a strong impact on both **how traders behave** and **how well they perform**. Fear periods amplify activity and risk‑taking, creating opportunities for skilled traders but losses for others. Segment‑aware, sentiment‑driven strategies can significantly improve performance and risk control.

---


Pallavi kumari 

Data Science Intern Applicant IIT Roorkee

---

*This project was completed as part of the Primetrade.ai hiring assignment.*
