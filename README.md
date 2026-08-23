# Log Fetcher : Multi-Application Universal Log Fetching Agent

An advanced, tool-enabled AI diagnostic agent designed to run inside Google Colab. 
The system uses Function Calling via the **Groq API** (with an **OpenAI failover fallback layer**) to dynamically query, sort, and isolate structural errors or text patterns across any target system or application log repository.

---

## 🚀 Key Features

*   **Universal Tool-Calling**: Leverages `llama-3.1-8b-instant` to analyze user intent and extract arguments for API logs fetches.
*   **High Availability Failover**: Automatically catches connection issues or rate limits, falling back from Groq immediately over to OpenAI (`gpt-3.5-turbo`).
*   **Dual-Layer Filtering Engine**: Supports structured metadata searches (by `severity level` or `component module`) combined with unstructured string keyword scanning (e.g., searching text blocks for "timeout" or "SKU").
*   **Colab Secrets Integration**: Safely references keys using Google Colab's native user-data vault environment.

---

## 🛠️ Getting Started in Google Colab

### 1. Set Up Environment Secrets
Before executing the script, map your private API tokens within your Google Colab workspace:
1. Click on the **Key Icon** (Secrets) in the left-hand sidebar menu.
2. Add a new secret named `GROQ_API_KEY` and insert your Groq API key.
3. Add an optional secret named `OPENAI_API_KEY` to act as your failover ecosystem layer.
4. Toggle **Notebook Access** to "On" for both keys.

### 2. Execution Setup
Run the following block inside your primary code cell to fulfill package dependencies:
```bash
!pip install groq -q
```

---

## 🧩 Architectural Code Workflow

