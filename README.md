# AI Intake & Triage Workflow

This project is an AI-powered intake and triage workflow built using **n8n** and the **OpenAI API**.

The workflow receives customer support requests, classifies them using an LLM, extracts structured information, routes them to the correct queue, applies escalation rules, and stores the final result in Google Sheets.

This project was created as part of a technical assignment to demonstrate workflow automation, LLM integration, and rule-based routing.

---

## Features

- AI-based classification (category, priority, confidence)
- Enrichment with structured data (issue summary, identifiers, urgency)
- Rule-based routing to support queues
- Escalation logic based on confidence and message conditions
- Structured output stored in Google Sheets
- End-to-end workflow built in n8n

---

## Tech Stack

- n8n
- OpenAI API
- JavaScript (Code nodes)
- Webhooks
- Google Sheets

---

## Demo Video

https://drive.google.com/file/d/1Bzzh-jecSbQnOtHkD0ElmBC18fuOUOcB/view?usp=sharing


## Structured Output (Google Sheet)

https://docs.google.com/spreadsheets/d/e/2PACX-1vRXXpd8BOlynbBywC_7DTysLLXpL4-iCur-sP4GGXLQWJssNGGqfESLtbKqtN8PdTm58asz5ZUhBCNi/pubhtml

The sheet contains all five required sample inputs with:

- category  
- priority  
- confidence  
- issue_summary (human-readable summary)  
- identifiers  
- urgency  
- destination_queue  
- escalation flag  

---

## Workflow File

The exported n8n workflow is included in this repository:
ai-intake-triage-workflow.json

You can import it into n8n using **Import from file**.

---

## Architecture

The workflow is triggered by a webhook, then uses two LLM calls:

1. Classification
2. Enrichment

The results are merged, routed using rules, checked for escalation, and saved to Google Sheets.

Routing rules:

- Bug Report → Engineering
- Feature Request → Product
- Billing Issue → Billing
- Technical Question → IT Support
- Incident/Outage → Engineering

Escalation rules:

- Low confidence
- Billing issue
- Down for all users

---

## Author

Jawad Ayash  
Computer Engineer  
Interested in backend, automation, and AI-driven systems

