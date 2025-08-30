# 🤖 Profiausba Aachen GmbH Chatbot Backend


Dies ist das Chatbot-Backend für die **Profiausba Aachen GmbH**.  
Es verarbeitet FAQs aus `faq.json`, bietet eine Admin-Seite zur Pflege und einen Chat-Endpoint mit GPT-Fallback.

---

## 🌐 Wichtige URLs

- **Admin-Seite (FAQ bearbeiten):**  
 <a href="https://profiausbau-chatbot-backend.onrender.com/admin.html" target="_blank">https://profiausbau-chatbot-backend.onrender.com/admin.html</a>
 
- **FAQ-API (liefert aktuelle faq.json):**  
 <a href="https://profiausbau-chatbot-backend.onrender.com/api/faq" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/faq</a>

 <a href="https://profiausbau-chatbot-backend.onrender.com/api/chat" target="_blank">https://profiausbau-chatbot-backend.onrender.com/api/chaT</a>


---

## ⚙️ Funktionen

- Verwaltung von FAQ-Daten (`faq.json`)  
- Separater Produktkatalog (`catalog.json`)  
- Chat-Endpoint mit FAQ-Matching (Fuse.js) und GPT-Fallback  
- Admin-Oberfläche mit Login & JSON-Editor  

---

## 📋 FAQ-Beispiele

So sieht die Struktur in `faq.json` aus:

```json

[
  {
    "frage": "Was kostet eine Badrenovierung?",
    "antwort": "Die Kosten h\u00e4ngen vom Zustand und Ihren W\u00fcnschen ab. Wir beraten Sie gern pers\u00f6nlich."
  },
  {
    "frage": "\u00dcbernehmt ihr auch Trockenbau?",
    "antwort": "Ja, Trockenbau geh\u00f6rt zu unseren Kernleistungen."
  }
]
