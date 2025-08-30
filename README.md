# 🤖 Profiausbau Aachen GmbH Chatbot Backend

Dies ist das Chatbot-Backend für die **Profiausbau Aachen GmbH**.  
Es verarbeitet FAQs aus der Datenbank (`faq`-Tabelle), bietet eine Admin-Seite zur Pflege und einen Chat-Endpoint mit GPT-Fallback.  
Caching erfolgt über **Redis (Upstash)**, Logs in **Postgres**.

---

## 🌐 Wichtige URLs

- **Admin-Seite (FAQ bearbeiten):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/admin.html" target="_blank">https://profiausbau-chatbot-backend.onrender.com/admin.html</a>

- **FAQ-API (aktuelle FAQs):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/api/faq" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/faq</a>

- **Chat-API (Chatbot Endpoint, POST mit `{ message }`):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/api/chat" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/chat</a>

- **Health-Check (für Monitoring):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/api/health" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/health</a>

---

## ⚙️ Funktionen

- Verwaltung von FAQ-Daten (Postgres-Tabelle `faq`)  
- Automatisches FAQ-Caching in Redis (Upstash)  
- Chat-Endpoint mit FAQ-Matching (Fuse.js)  
- GPT-Fallback (OpenAI GPT-4o)  
- Admin-Oberfläche mit Login, JSON-Editor & FAQ-Kandidaten  
- Speicherung aller Chat-Logs (`chat_log` Tabelle in Postgres)  

---

## 🚀 Setup (lokale Entwicklung)

```bash
# Repository klonen
git clone <repo-url>
cd chatbot-backend

# Abhängigkeiten installieren
npm install

# Umgebungsvariablen setzen (.env)
cp .env.example .env
# trage DATABASE_URL, UPSTASH_REST_URL, UPSTASH_REST_TOKEN, OPENAI_API_KEY, OPENAI_ORG_ID ein

# Server starten
node server.js


[
  {
    "frage": "Was kostet eine Badrenovierung?",
    "antwort": "Die Kosten hängen vom Zustand und Ihren Wünschen ab. Wir beraten Sie gern persönlich."
  },
  {
    "frage": "Übernehmt ihr auch Trockenbau?",
    "antwort": "Ja, Trockenbau gehört zu unseren Kernleistungen."
  }
]

🔄 Systemübersicht (Mermaid Diagramm)
flowchart TD
    A[User Nachricht] --> B[Chat Endpoint /api/chat]
    B --> C{FAQ Match?}
    C -->|Ja| D[Antwort aus Postgres FAQ]
    C -->|Nein| E[GPT Fallback (OpenAI)]
    D --> F[Antwort an User]
    E --> F[Antwort an User]
    F --> G[Speichern in Postgres chat_log]
    D --> H[Optional Redis Cache]
    E --> H

---
📦 Technologien
Node.js + Express → REST API
Postgres (Supabase/Render) → FAQ + Chat-Logs
Redis (Upstash) → FAQ Cache
Fuse.js → FAQ-Suchalgorithmus (Fuzzy Search)
OpenAI GPT-4o → KI-Antworten
GitHub Actions → Automatisierte Katalog/LLMS-Updates
Render → Hosting
---
👨‍💻 Maintainer

Profiausbau Aachen GmbH
📧 info@profiausbau.com

