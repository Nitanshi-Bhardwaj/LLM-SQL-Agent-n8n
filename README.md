# SQL Agent (LLM) in n8n — Online Retail II (MySQL + Ollama)

An **agentic Text-to-SQL assistant** built in **n8n** that converts natural-language questions into **MySQL queries** and returns analytics results on the **Online Retail II** transactions dataset.  
The agent uses **tool-calling** (MySQL “Execute Query” as a tool) and **conversational memory**, and runs locally with **Docker** + **Ollama** (no paid API key required).

---

## Features
- **Agentic workflow in n8n**: chat → LLM agent → SQL tool → result summary
- **Text-to-SQL** with guardrails:
  - SELECT-only
  - MySQL strict `ONLY_FULL_GROUP_BY` compliant
  - limits raw row outputs
- **Local and reproducible** with Docker
- **Free model runtime** via Ollama (local LLM)

---

## Architecture
**Chat Trigger (n8n)** → **AI Agent (LLM)** → **MySQL Tool (Execute Query)** → **Response (answer + SQL + interpretation)**  
Optional: **Simple Memory** node for multi-turn context.

---

## Dataset
This project uses the **UCI Online Retail II** dataset (Excel).  
**Note:** The dataset is not committed to this repository due to size and licensing; you download it locally.

Dataset source (copy/paste into your browser):
```text
https://archive.ics.uci.edu/ml/datasets/Online+Retail+II
