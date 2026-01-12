# n8n GenAI Chatbot Backend

This repository contains the n8n workflow, infrastructure configuration, and database initialization for the AI Chatbot project.

## 🚀 Overview

The backend is built using **n8n** as the primary orchestration engine, leveraging **PostgreSQL** for memory and **Redis** for message queuing. It provides a robust API for a React-based frontend to interact with multiple AI capabilities.

![n8n Workflow Screenshot](./workflow_screenshot.png)

## 📁 Key Files

- `workflow.json`: The complete n8n workflow definition.
- `docker-compose.yml`: Local development setup for n8n, PostgreSQL, and Redis.
- `render.yaml`: Deployment configuration for Render.
- `init.sql`: Database schema for chat memory and scheduling.
- `▶️ Chatbot - Single Workflow - n8n.pdf`: Visual representation of the n8n workflow.

## ✨ Features Implemented

- **Speech-to-Text (STT)**: Integration with OpenAI Whisper for transcribing audio messages.
- **Image-to-Text (ITT)**: Integration with OpenAI Vision for analyzing image attachments.
- **Memory Management**: Persistent chat history stored in PostgreSQL.
- **Redis Message Queue**: Batched processing of multiple user messages.
- **Message Splitting**: Intelligent output formatting into multiple response bubbles.
- **Custom Tools**:
  - Availability checking
  - Appointment booking
  - Automated follow-up scheduling
- **Follow-up System**: Continuous checking (every minute) for scheduled follow-ups via primary and secondary triggers.

## 🛠️ Setup & Deployment

### Local Development

1. Clone the repository.
2. Create a `.env` file with your `OPENAI_API_KEY`.
3. Run `docker-compose up -d`.
4. Access n8n at `http://localhost:5678`.
5. Import `workflow.json`.

### Deployment

This project is configured for one-click deployment to **Render** via the provided `render.yaml` blueprint.

---

_Note: For a visual guide to the n8n nodes and logic, refer to the [n8n Workflow PDF](./▶️ Chatbot - Single Workflow - n8n.pdf)._
