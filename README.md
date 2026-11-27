# 🌐 Website Uptime Monitor (n8n)

A simple, no-code/low-code automation built with **[n8n](https://n8n.io)** that checks whether a list of websites is online and produces a single status report showing which sites are **UP** and which are **DOWN**.

![Workflow](screenshot.png)

---

## ✨ Features

- Monitors multiple websites in one run
- Sends an HTTP request to each site and checks the response
- Combines all results into one clean summary report
- Easy to extend with scheduled runs and alerts (Email, Slack, Telegram, WhatsApp)

---

## ⚙️ How It Works

| # | Node | What it does |
|---|------|--------------|
| 1 | **Manual Trigger** | Starts the workflow when you click *Execute workflow* |
| 2 | **Code in JavaScript** | Defines the list of websites to monitor (outputs one item per URL) |
| 3 | **HTTP Request** | Sends a request to each website and captures the response/status code |
| 4 | **Code in JavaScript1** | Processes all responses and builds a single uptime report |

```
Manual Trigger → Website List (Code) → HTTP Request → Status Report (Code)
```

---

## 🚀 Getting Started

### Prerequisites
- n8n installed (self-hosted or n8n Cloud)
  - Quick start: `npx n8n` → open `http://localhost:5678`

### Import the workflow
1. Download `Website Uptime Monitor.json` from this repository
2. In n8n, go to **Workflows → Import from File**
3. Select the JSON file
4. Open the first **Code** node and replace the URLs with the websites you want to monitor
5. Click **Execute workflow**

---

## 📊 Sample Output

```json
{
  "totalSites": 3,
  "up": 2,
  "down": 1,
  "results": [
    { "url": "https://example.com", "status": "UP", "statusCode": 200 },
    { "url": "https://google.com", "status": "UP", "statusCode": 200 },
    { "url": "https://some-broken-site.com", "status": "DOWN", "statusCode": null }
  ]
}
```

---

## 🛠️ Tech Stack

- **n8n** – workflow automation
- **JavaScript** – custom logic in Code nodes
- **HTTP Request node** – website health checks

---

## 🔮 Future Improvements

- [ ] Replace manual trigger with a **Schedule Trigger** (e.g. every 5 minutes)
- [ ] Send alerts via **Email / Slack / Telegram / WhatsApp** when a site goes down
- [ ] Log results to **Google Sheets** for uptime history
- [ ] Track response time and flag slow websites

---

## 👤 Author

**Shahid Raza**
GitHub: [@ShahidRazaPro](https://github.com/ShahidRazaPro)

⭐ If you found this useful, consider giving the repo a star!
