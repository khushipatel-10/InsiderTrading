
# 💼 Insider Surveillance & Reporting (ISR) Project

A full-stack investigative dashboard and analytics pipeline for detecting **potential insider trading activities**. This project combines **real-time market surveillance**, **visual insights**, **AI-powered fraud detection**, and **interactive dashboards** using **Shiny (R)** and **Python**. It is designed to assist regulatory bodies or compliance analysts in identifying unusual trading behavior through a visually immersive interface.

## 📽️ Demo

🎥 [Watch the Walkthrough Video](https://www.youtube.com/watch?v=GEdgE4XvqRs&t=2s)

## 🌐 Live Deployment

> Currently deployed locally or via ShinyApps.io (instructions below to run or deploy)

---

## 🧠 Key Highlights

- **📊 Network Graphs for Insider–Company Links**  
  Visualizes insider connections using Neo4j-style relationship graphs powered by `visNetwork`.

- **📈 Market Anomaly Detection with Prophet**  
  Predicts expected market behavior for top S&P 50 companies and flags anomalous trading days.

- **🤖 AI-Powered GPT-3.5 Fraud Reasoning**  
  Integrates OpenAI's API to generate investigative reasoning on suspected trades using real-world news.

- **📥 Real-Time News Scraping**  
  News articles are pulled using `apilayer` or `yahoo_fin` based on date and ticker metadata.

- **📁 Modular Architecture**  
  Codebase organized into Shiny modules (`src/components/modules`) and pages (`src/pages/`) for full maintainability.

---

A powerful AI-enabled platform to investigate potential insider trading through stock anomaly detection, contextual news analysis, and relationship mapping. Built with **R (Shiny)** for UI, **Python (Prophet + OpenAI)** for intelligence, and enhanced with interactive network visualizations and streaming news integrations.

---

## 🧠 How It Works – AI + Prophet Forecasting Pipeline

1. **Takes input**: Suspicious stock trade details (Company + Date).
2. **Fetches stock prices** from Yahoo Finance historical data.
3. **Applies Prophet Forecasting** to detect abnormal price jumps/dips.
4. **If anomaly is detected**:
   - Scrapes news articles before the trade date.
   - Passes them to GPT-4.0 to investigate possible insider behavior.
5. **Outputs**:
   - An **AI-generated natural language report**
   - A **visual graph of insider–company relationships**
   - A **data table of suspicious trade details**

---

## ⚙️ Setup Instructions

### 🔧 Requirements

- **R Version**: ≥ 4.2  
- **Python Version**: ≥ 3.10  
- **Required Packages**:

| Language | Packages |
|----------|----------|
| R        | shiny, visNetwork, DT, shinyWidgets, reticulate, dplyr, readr, plotly |
| Python   | prophet, openai, yahoo_fin, pandas, numpy, requests, tqdm |

---

### 📦 R Setup


install.packages(c(
  "shiny", "shinyWidgets", "visNetwork", "DT", 
  "reticulate", "plotly", "dplyr", "readr"
))

---

## 🧪 Example Use Case

- **Input**: `AAPL` on `2024-04-01`  
- **Detected**: Abnormal price surge  
- **Reasoning**: GPT summarized pre-trade news showing a private deal announcement  
- **Verdict**: Possible insider signal flagged  

---

## 🧬 Features

- 🔍 **Stock anomaly detection** using Meta Prophet  
- 🤖 **AI reasoning** using GPT-3.5  
- 📰 **News context analysis**  
- 🔗 **Insider–Company relationship graphs** via `visNetwork`  
- 📊 **Interactive dashboard** (Shiny)  
- ☁️ **Deployable to ShinyApps.io**  

---

## 👨‍👩‍👧‍👦 Contributors

Built with dedication by **Team FOXTROT**:

- **Dishant Zaveri**  
- **Navya Unnikrishnan**  
- **Rahul Baid**  
- **Khushi Patel**  

💡 Ideation | 📊 Modeling | 🖼️ UI/UX | 🤖 AI Integration | 🌐 Deployment

---

## 📄 References

- [OpenAI GPT-3.5 API](https://platform.openai.com/)  
- [Facebook Prophet Forecasting](https://facebook.github.io/prophet/)  
- [Yahoo Finance API](https://theautomatic.net/yahoo_fin-documentation/)  
- [SGX Insider Trading Guidelines](https://www.sgx.com/regulation)

---

## 📬 Contact

- Email: [dishant.zaveri@tamu.edu](mailto:dishant.zaveri@tamu.edu)  
- GitHub: [dishantzaveri](https://github.com/dishantzaveri)

---

## 📌 License

This project is for **educational and academic use only**.  
Please **credit the authors** when reusing or referencing.

---

## ✅ Future Work

- 🔔 Add alert system for real-time trade monitoring  
- 📄 Integrate SEC EDGAR filings  
- 🌎 Expand to multi-market (e.g., NYSE, SGX, NSE)  
- 🔄 Auto-refreshing visual dashboards  


## 🧭 Project Structure

```plaintext
isrproject/
│
├── db/                         # Data directory
│   ├── NASDAQ/                # Insider CSVs and metadata
│   ├── clustering/data/       # Preprocessed clustering outputs
│   └── pickle/                # Trained Prophet models (.pkl)
│
├── src/
│   ├── components/            # Shiny modules and custom layouts
│   ├── pages/                 # Page-level UI/server files
│   └── widgets/               # Custom widgets like chat, cards
│
├── www/                       # Static assets (CSS/JS)
├── train.py                  # Python script to train Prophet model per stock
├── app.R / global.R          # Shiny entrypoint
└── README.md
