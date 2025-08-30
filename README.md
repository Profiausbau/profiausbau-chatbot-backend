# 🤖 Profiausbau Aachen GmbH Chatbot Backend

Dies ist das Chatbot-Backend für die **Profiausbau Aachen GmbH**.  
Es verarbeitet FAQs aus der Datenbank (`faq`-Tabelle, gepflegt über Admin-Panel), nutzt Redis-Caching zur Beschleunigung und bietet einen Chat-Endpoint mit GPT-Fallback.

---

## 🌐 Wichtige URLs

- **Admin-Seite (FAQ bearbeiten):**  
  [https://profiausbau-chatbot-backend.onrender.com/admin.html](https://profiausbau-chatbot-backend.onrender.com/admin.html)

- **FAQ-API (liefert aktuelle FAQ-Einträge):**  
  [https://profiausbau-chatbot-backend.onrender.com/api/faq](https://profiausbau-chatbot-backend.onrender.com/api/faq)

- **Chat-Endpoint (POST mit `{ message }`):**  
  [https://profiausbau-chatbot-backend.onrender.com/api/chat](https://profiausbau-chatbot-backend.onrender.com/api/chat)

- **Health Check (für Monitoring):**  
  [https://profiausbau-chatbot-backend.onrender.com/api/health](https://profiausbau-chatbot-backend.onrender.com/api/health)

---

## ⚙️ Funktionen

- Verwaltung von FAQ-Daten in der PostgreSQL-Datenbank (`faq`-Tabelle)  
- Redis Cache (Upstash) für schnelle FAQ-Abfragen  
- Chat-Endpoint mit FAQ-Matching (Fuse.js) und GPT-Fallback  
- Admin-Oberfläche mit Login & JSON-Editor  
- Logging von Chatverläufen in der Tabelle `chat_log`  
- Health-Endpoint (`/api/health`) für Monitoring und Warm-Up  

---

## 📋 FAQ-Beispiele

So sieht die Struktur der FAQ-Daten aus (Beispieleinträge aus der Datenbank):

```json
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
