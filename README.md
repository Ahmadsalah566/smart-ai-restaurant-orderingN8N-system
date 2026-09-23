# 🍕 Smart AI Restaurant Ordering & Delivery System

A multi-agent AI solution built on **n8n** that automates customer food ordering, menu navigation, dynamic delivery calculation, and real-time state management via **Telegram Bot API** and **Google Gemini LLM**.

---

## 🏛️ Multi-Agent Architecture

The system utilizes a **Main Orchestrator (Gatekeeper Agent)** to parse user intents and delegate tasks to specialized sub-agents:

1. **Main Orchestrator (Gatekeeper Agent):**
   - Classifies customer inputs, enforces strict safety protocols (abuse prevention), and filters protocol tags (`DATA:`, `MESSAGE_TO_CUSTOMER:`) from public outputs.
2. **Customer Agent:**
   - Captures, validates, and manages customer contact profiles.
3. **Orders Agent:**
   - Handles menu inquiries, item customizations, order additions, and total bill calculations.
4. **Delivery Agent:**
   - Validates delivery locations and computes dynamic delivery fees based on distance and order parameters.

---

## 🌟 Key Capabilities & Engineering Highlights

- **Safety & Conduct Guardrails:** Automatically identifies abusive language and issues formal warnings prior to session termination.
- **State Management & Upserting:** Uses `Chat ID` as a primary key in **Google Sheets** to support order updates and append operations seamlessly without duplicate entries.
- **Optimized LLM Execution:** Powered by `gemini-2.5-flash` to bypass thought signature overhead and achieve fast response times.

---

## 🛠️ Tech Stack

- **Orchestration:** n8n
- **AI Core:** Google Gemini API (`gemini-2.5-flash`)
- **Messaging:** Telegram Bot API
- **Database / State Storage:** Google Sheets API
- **Logic & Parsing:** JavaScript (Node.js)

---

## 🚀 Setup & Deployment

1. Download the `workflow.json` file from this repository.
2. Import the file into your **n8n** environment.
3. Set up your **Telegram Bot**, **Google Gemini**, and **Google Sheets** API credentials.
4. Activate the trigger node and start accepting automated orders!
