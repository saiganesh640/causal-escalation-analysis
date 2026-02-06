# Causal Escalation Analysis

This project implements a **deterministic, evidence-grounded causal analysis system** over customer–agent conversational transcripts.  
The goal is to explain **why escalations happen**, not to predict them, by extracting transparent causal factors directly from conversation data.

---

## Overview
This project focuses on **understanding and explaining customer support escalations** by analyzing customer–agent conversations.

Instead of predicting outcomes using black-box machine learning models, this system is built around **deterministic, rule-based causal reasoning**. Every explanation provided by the system is **directly supported by real conversational evidence**, making the results transparent, auditable, and trustworthy.

The project was developed as part of a **Data Science Hackathon**, with a strong emphasis on explainability, reproducibility, and evaluation readiness.

---

## Problem Statement
Customer escalations are costly and often poorly understood. While many systems can detect or predict escalations, they usually fail to clearly answer:

- *Why did this escalation happen?*
- *Which parts of the conversation caused it?*
- *What concrete evidence supports this explanation?*

This project addresses these questions by performing **causal analysis over conversational data**, grounded entirely in the dataset itself.

---

## Project Objectives
- Analyze customer–agent conversations at a **turn level**
- Identify **dialogue patterns that contribute to escalation**
- Provide **message-level evidence** for every causal factor
- Support **interactive, multi-turn analytical queries**
- Produce **deterministic and reproducible outputs** suitable for evaluation

---

## Design Philosophy
- **Faithfulness over prediction** – no unsupported explanations
- **Rule-based reasoning** instead of opaque ML models
- **Evidence grounding** using verbatim conversation turns
- **Consistency across follow-up queries**
- **Hackathon-friendly architecture** with clear evaluation artifacts

---

##  System Architecture

### 1. Data Ingestion & Normalization
- Input data consists of conversation-level JSON transcripts
- Each conversation is converted into a **turn-level representation**
- This allows causal signals to be detected at the exact message where they occur

**Each turn includes:**
- `call_id`
- `turn_id`
- `speaker` (customer / agent)
- `text`
- Metadata (domain, intent, reason_for_call)
- Deterministic outcome label

---

### 2️. Outcome Mapping
- Conversation outcomes are assigned **deterministically**
- Uses available metadata and explicit lexical cues
- Ensures results are reproducible and auditable

---

### 3️. Causal Reasoning Layer
Escalation-driving factors are defined using transparent, rule-based patterns identified through exploratory analysis.

Examples include:
- Delay or deflection by the agent
- Repeated unresolved issues
- Explicit escalation requests
- Lack of proactive notification
- High urgency or business impact


---

### 4️. Interactive Query Interface
- Initial query returns a complete causal explanation
- Follow-up queries reuse stored context
- Ensures consistent answers across multi-turn interactions



---

### 5️. Evaluation & Export
- Predefined queries are executed automatically
- Outputs are captured in structured JSON format
- Results are exported as **submission-ready CSV files**
- Enables clear auditing and repeatable evaluation

---

##  Technology Stack
- **Language:** Python
- **API Framework:** FastAPI
- **Server:** Uvicorn
- **Data Processing:** JSON, CSV
- **HTTP Requests:** Requests library

The stack is intentionally minimal to keep execution predictable and lightweight.

---

##  Project Structure
<img width="451" height="646" alt="Screenshot 2026-02-07 031434" src="https://github.com/user-attachments/assets/274127ac-3df5-431c-a80f-18bc9fabe632" />

---

##  Evaluation Metrics
- **ID Recall:** Correct retrieval of relevant call IDs
- **Faithfulness:** Evidence-backed explanations
- **Relevance:** Factors specific to escalation
- **Consistency:** Stable follow-up responses
- **Reproducibility:** Identical outputs on returns

---

##  Limitations
- Rule-based logic depends on explicit wording
- Rare or implicit patterns may be missed
- Explains observed causes, not counterfactuals

These limitations are intentional trade-offs for transparency and speed.

---

##  Future Scope
- Extend rule library with new causal patterns
- Add lightweight UI for exploration
- Improve coverage using semi-automated rule discovery
- Integrate analytics dashboard

---


