
# 🤖 AI-Powered Event Attendant & Contract Generator

Automated system built with **n8n** that handles customer service for an event via Telegram using AI, and automatically generates personalized contracts when a registration form is submitted.

---

## 📌 Overview

This project consists of **two complementary automated workflows**:

1. **AI Attendant** — Handles customer inquiries on Telegram, answers questions about the event using an AI agent with memory and knowledge base, and sends the registration link when the customer decides to sign up.

2. **Contract Generator** — Triggered when the registration form is submitted. Automatically creates a personalized contract in Google Drive, sends it via Telegram, and emails a confirmation to the registrant.

---

## 🔁 Workflow 1 — AI Attendant (Telegram)

### What it does
- Receives messages via **Telegram** (text, image, or audio)
- Identifies the type of media and routes accordingly using a **Switch node**
- Transcribes audio messages using **Whisper (OpenAI)**
- Analyzes images with **OpenAI Vision**
- Uses an **AI Agent** with memory and a custom knowledge base to answer questions about the event
- Convinces the customer to register and sends the form link
- Sends personalized responses back via **Telegram**

### Tools & Nodes Used
- Telegram Trigger
- Switch (message routing)
- OpenAI (image analysis + audio transcription)
- AI Agent with Simple Memory
- Knowledge Base (custom document)
- Loop Over Items + Split Out
- Formatter

### Workflow Preview
![Workflow 1 - AI Attendant](./images/workflow1.png)

---

## 🔁 Workflow 2 — Contract Generator (Form → Google Drive → Notification)

### What it does
- Triggered by a **form submission**
- Copies a contract **template** from Google Drive
- Updates the document with the **customer's personalized data**
- Downloads the completed contract
- Sends the contract to the responsible person via **Telegram**
- Sends an **email confirmation** to the person who filled out the form

### Tools & Nodes Used
- On Form Submission
- Google Drive (Copy + Download)
- Google Docs (Update document)
- Telegram (Send document)
- Gmail (Send confirmation email)

### Workflow Preview
![Workflow 2 - Contract Generator](./images/workflow2.png)

---

## 🔗 How the Workflows Connect


Customer contacts on Telegram
        ↓
[Workflow 1] AI Attendant responds and convinces customer
        ↓
Customer fills out the registration form
        ↓
[Workflow 2] Contract is generated and sent automatically




## 🛠 Tech Stack

| Tool | Usage |
|------|-------|
| n8n | Workflow automation |
| Telegram API | Customer communication channel |
| OpenAI (GPT-4 + Whisper) | AI agent, image analysis, audio transcription |
| Google Drive | Contract template storage and management |
| Google Docs | Dynamic document generation |
| Gmail | Email confirmation to registrant |

---

## 💡 Key Features

- ✅ Handles text, image, and audio messages automatically
- ✅ AI with persistent memory for natural conversations
- ✅ Custom knowledge base specific to the event
- ✅ Fully automated contract generation with personalized data
- ✅ Multi-channel notification (Telegram + Email)
- ✅ Zero manual intervention after initial setup

## 📲 Other Supported Channels

Although this implementation uses **Telegram**, the same automation logic can be easily adapted to work with **WhatsApp** and **Instagram Direct** — just swap the messaging nodes in n8n. The AI agent, memory, knowledge base, and contract generation flows remain exactly the same.

---

## 👩‍💻 Author

Built by **[Your Name]** — Automation & AI enthusiast.

Connect with me on [LinkedIn](https://www.linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)
