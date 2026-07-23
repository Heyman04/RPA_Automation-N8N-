# 🔄 Project DAWN – Multi-LLM Orchestration & Logging Workflow

**DAWN** is an automated multi-model AI orchestration pipeline built using **n8n**. It routes incoming user messages or webhook payloads across multiple Large Language Model (LLM) agents simultaneously, aggregates/merges their outputs, returns the structured response back via Webhook, and archives all interactions directly into **MongoDB**.

---

## 🌟 Features

* **Multi-LLM Parallel Execution**: Dispatches queries to multiple AI agents running different models in parallel:
  * **Groq** (`Groq Chat Model`)
  * **Google Gemini** (`Google Gemini Chat Model`)
  * **Ollama** (`Ollama Chat Model` – Local/Self-hosted)
  * **OpenRouter** (`OpenRouter Chat Model`)
  * **Mistral AI** (`Mistral Cloud Chat Model`)
* **Dual Trigger System**:
  * **Webhook Integration**: Accept incoming JSON requests via `POST` requests.
  * **Native Chat Interface**: Test queries directly using n8n's native `When chat message received` trigger.
* **Response Aggregation**: Uses an n8n **Merge** node to combine model outputs before returning a single formatted output via `Respond to Webhook`.
* **Database Logging**: Captures incoming inputs, intermediate agent outputs, and metadata directly into a **MongoDB** collection for audit, fine-tuning, or analytics.

---

## 🏗️ Architecture & Flow