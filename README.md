# <p align="center">🔮 IG-Organiser Bot 🔮</p>

<p align="center">
  <img src="https://img.shields.io/badge/SYSTEM_STATUS-ACTIVE-00FF00?style=for-the-badge&logo=statuspage&logoColor=black" />
  <img src="https://img.shields.io/badge/RUNTIME-MAKE.COM-FF6600?style=for-the-badge&logo=make&logoColor=white" />
  <img src="https://img.shields.io/badge/AI_ENGINE-GEMINI_1.5-8E75FB?style=for-the-badge&logo=googlegemini" />
</p>

---

## 📝 PROJECT OVERVIEW
Name: @Builderxoxo_bot<br>
Video Link: https://drive.google.com/file/d/1w12lkVXBZ2A-weoZsBoih76RTMKw0jao/view <br><br>
**IG-VibeVault** is an event-driven ETL pipeline designed to solve the problem of social media link rot. By intercepting Instagram content via **Webhooks**, the system utilizes **NLP-based sentiment analysis** to extract "vibes" and summaries, storing them in a persistent, searchable cloud database.

---

## 🛠 TECH SPECIFICATIONS

| LAYER | TECHNOLOGY | ROLE |
| :--- | :--- | :--- |
| **Ingestion** | `Telegram/WhatsApp API` | Webhook Interface & Command Entry |
| **Scraper** | `Apify SDK` | Synchronous Headless Metadata Extraction |
| **Intelligence** | `Google Gemini 1.5` | Zero-Shot Summary & Tag Generation |
| **Persistence** | `Google Sheets API` | SQL-like Cloud Storage & Dashboard |
| **Orchestrator** | `Make.com` | Conditional Logic & Flow Management |

---
<img width="1784" height="854" alt="image" src="https://github.com/user-attachments/assets/224935e6-d469-4177-87b2-091f1e2d6ec2" />

## 🧠 SYSTEM ARCHITECTURE

The core logic uses a **Conditional Branching Router** to bifurcate traffic based on the payload content.

```mermaid
graph TD
    User((User)) -- "Post/Keyword" --> W[Webhook Trigger]
    W --> R{Logic Router}
    
    subgraph SAVER_LOGIC [Branch A: Save Link]
    R -- "instagram.com" --> S[Apify Scraper]
    S --> G[Gemini AI Analysis]
    G --> GS[(Google Sheets)]
    GS --> C[Push Notification]
    end

    subgraph SEARCH_LOGIC [Branch B: Query Vault]
    R -- "Plain Text" --> QR[Sheet Search]
    QR --> AG[Text Aggregator]
    AG --> U[Formatted Results List]
    end

    style R fill:#f96,stroke:#333,stroke-width:2px
    style G fill:#8E75FB,color:#fff
