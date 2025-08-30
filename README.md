# 🤖 Profiausbau Aachen GmbH Chatbot Backend

Dies ist das Chatbot-Backend für die **Profiausbau Aachen GmbH**.  
Es verarbeitet FAQs aus der Datenbank (`faq`), bietet eine Admin-Seite zur Pflege und einen Chat-Endpoint mit GPT-Fallback.

---

## 🌐 Wichtige URLs

- **Admin-Seite (FAQ bearbeiten):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/admin.html" target="_blank">https://profiausbau-chatbot-backend.onrender.com/admin.html</a>
 
- **FAQ-API (liefert aktuelle FAQ-Einträge):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/api/faq" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/faq</a>

- **Chat-Endpoint (POST mit `{ message }`):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/api/chat" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/chat</a>

- **Health-Check (für Monitoring):**  
  <a href="https://profiausbau-chatbot-backend.onrender.com/api/health" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/health</a>

---

## ⚙️ Funktionen

- Verwaltung von FAQ-Daten (PostgreSQL `faq`-Tabelle)  
- Chat-Endpoint mit **FAQ-Matching** (Fuse.js) und **GPT-Fallback**  
- Admin-Oberfläche mit Login, JSON-Editor und Cache-Verwaltung  
- Speicherung aller Chats in `chat_log` (inkl. Quelle: `faq` oder `gpt`)  
- Automatische **FAQ-Kandidaten** aus echten Nutzerfragen  

---

## 📋 FAQ-Beispiele

So sieht die Struktur in der FAQ-Datenbank (`faq`) aus:

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
