# 🧠 TokenWise — Real-Time Wallet Intelligence on Solana

TokenWise is a real-time analytics platform that monitors and analyzes top wallet activity for a specific Solana token. It helps surface powerful insights like whale movements, protocol usage, and market direction — all through a clean, filterable dashboard.

---

## 🚀 Features

- 🧾 **Top 60 Wallet Discovery** (cached every 5 minutes using Redis)
- 🔄 **Real-Time Buy/Sell Monitoring** via Helius Webhooks
- 🛠️ **DEX Protocol Detection** (Jupiter, Raydium, Orca)
- 📈 **Dashboard Insights**
  - Total Buys vs Sells
  - Net Flow (Buy-heavy/Sell-heavy)
  - Most Frequent Wallets
  - Protocol Usage Breakdown
  - Highest wallets by amount
  - Transaction summary
- 📆 **Historical Filtering** (1h, 6h, 1d, 2d, 7d, custom range)
- 📤 **Export to CSV/JSON**
- 🔁 **Paginated Transaction Table**
- 📊 **Charts and Visualizations**

---

## 🏗 Architecture Overview

[SOLANA RPC + Helius]
↓
[Top Holder Fetcher (Scheduler)] → [Redis Cache (5 min TTL)]
↓
[Webhook Listener (Ngrok + Helius)] → [Spring Boot Backend] → [PostgreSQL]
↓
[REST APIs]
↓
[React Frontend Dashboard]



---

## 📦 Tech Stack

| Layer         | Tech Used                          |
|--------------|------------------------------------|
| Backend       | Java 17, Spring Boot, Redis, PostgreSQL |
| Frontend      | React, Axios, Chart.js / Recharts |
| Blockchain    | Helius API, Solana RPC            |
| Other         | Ngrok (for webhook tunneling)     |

---

## ⚙️ Setup Instructions

### 🛠 Backend

```bash
cd backend
./mvnw spring-boot:run
Environment Variables:

HELIUS_API_KEY

MINT_ADDRESS

WEBHOOK_URL

PostgreSQL DB config

Webhooks Setup (with Ngrok):

Start ngrok: ngrok http 8080

Register webhook with Helius using the public URL

💻 Frontend
bash
Copy
Edit
cd frontend
npm install
npm start
Environment:

REACT_APP_API_URL=http://localhost:8080

🧪 Sample Output Data
Sample exported files:

transactions-last-1day.csv

transactions-last-1day.json

Each file includes:

Timestamp

Wallet Address

Direction (Buy/Sell)

Token Amount

Protocol Used

📊 Dashboard Preview

Key Sections:

📈 Buy/Sell Charts

🧠 Smart Wallet Activity

🛠 Protocol Leaderboard

📆 Custom Time Range Filters

📤 Export Controls


🔮 Future Enhancements
🔔 Email/Discord Alerts for large transactions

🧩 Wallet Clustering (same-user detection)

📲 Mobile-friendly dashboard

🧠 Predictive trend modeling using basic ML

🌐 Full deployment on Vercel + Render

🙋‍♀️ About Me
I'm Arpita, a backend engineer passionate about blockchain and real-time systems. This project reflects my love for clean architecture, scalable systems, and user-focused dashboards.

📬 Contact
Feel free to connect for feedback or questions!



---

