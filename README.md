# HVAC BOQ Copilot – Intelligent Search, Cost Estimation & Anomaly Engine

### A Gemini-powered AI agent that transforms HVAC BOQ data into instant search, quoting, budgeting, and cost-risk insights.

---

## 🚀 Overview

HVAC BOQ Copilot is a multi-tool AI agent built using the Google Agent Development Kit (ADK) and Gemini 2.5 Flash Lite.  
It turns a static HVAC BOQ dataset into a powerful interactive assistant capable of:

- 🔍 Smart item search  
- 🧾 Automatic quotation generation  
- 📊 Construction cost estimation  
- ⚠️ Price anomaly detection  
- 🤝 Vendor comparison (optional future extension)  
- 📁 Multi-step project budgeting and forecasting  

This project serves as a business-focused + data-science-focused capstone, showcasing real-world AI automation for the HVAC supply, service, and maintenance industry.

---

## 🧩 Problem Statement

HVAC engineers, sales teams, contractors, and estimators often face these challenges:

- Manual BOQ lookups across hundreds of items  
- Time-consuming item filtering (pipe sizes, duct items, valves, fittings, etc.)  
- Slow quotation preparation  
- Human errors in pricing & units  
- Difficulty spotting unusual or suspicious price entries  
- Inefficient vendor cost comparison  

These inefficiencies affect bidding speed, project budgeting accuracy, and profitability.

HVAC BOQ Copilot solves this by turning the dataset into an intelligent, conversational agent.

---

## 🤖 Why Agents?

Traditional scripts cannot:

- Understand natural-language queries (“show me 300mm pipe items”)  
- Make decisions about when to call tools  
- Explain cost anomalies conversationally  
- Manage multi-step interactions (e.g., quote + add another item + compare costs)  
- Reason across vague or fuzzy inputs  

AI agents, however:

- Understand HVAC-specific language  
- Autonomously choose tools  
- Combine reasoning + data + actions  
- Maintain session memory for multi-step workflows  

Agents transform this from a dataset into a real assistant.

---

## 🏗️ System Architecture

User Query  
   │  
   ▼  
HVAC BOQ Copilot (Gemini LLM Agent)  
   ├── search_items_tool → Find relevant HVAC BOQ items  
   ├── generate_quote_tool → Create multi-item project quotes  
   ├── cost_anomaly_tool → Detect abnormal pricing  
   ├── vendor_compare_tool (optional) → Compare vendor pricing  
   ▼  
Structured Final Response  

### Components

- Google ADK → Agent orchestration  
- Gemini 2.5 Flash Lite → Reasoning + natural language  
- Tools (Python functions) → Search, quoting, anomaly detection  
- In-Memory Session Service → Multi-turn interactions  
- HVAC BOQ Dataset → CSV with item code, category, name, unit, price  

---

## 🎮 Demo Capabilities

### 🔍 1. Smart Search

User: `Search items related to 300mm and show top 5.`  
Agent: Returns a table with item code, name, unit, price.

### 🧾 2. Quote Generation

User: `Create a quote for 40 RFT of 300mm pipe.`  
Agent: Calculates cost and returns a structured quote table.

### 📊 3. Cost Estimation

User: `Estimate total cost for 300mm, 200mm, and 150mm pipes (10 RFT each).`

### ⚠️ 4. Price Anomaly Detection

User: `Check price anomalies for pipe category.`

### 🤝 5. Vendor Comparison (Optional Future Feature)

User: `Compare vendor A and B for duct materials.`

---

## 📁 Dataset Description

Columns in `Boq_dataset.csv`:

| Column Name         | Description                                    |
|---------------------|------------------------------------------------|
| Item code           | Unique ID                                      |
| Item Category       | Pipe, duct, service, equipment, etc.           |
| Item Name           | Material description                           |
| Measurement Unit    | RFT, Nos, Sqft, Month, etc.                    |
| Price               | Numeric price (cleaned)                        |

743 items total.

---

## 🔧 Tools Used (Tech Stack)

### Core AI / Agent Platform

- Google Agent Development Kit (ADK)  
- Gemini 2.5 Flash Lite  

### Programming

- Python  
- Pandas  
- NumPy  

### Notebook Environment

- Kaggle Notebooks / Jupyter  

### Data Science Techniques

- Text preprocessing  
- Fuzzy matching (optional)  
- Statistical anomaly detection  
- Quote aggregation  

---

## 🧱 How It Works – The Build

### ✔ Step 1: Load and Clean BOQ Dataset

- Fix price formatting (remove commas, convert to float)  
- Standardize item names  
- Clean missing measurement units  

### ✔ Step 2: Create Python Tools

- `search_items(keyword, top_k)`  
- `generate_quote(item, qty)`  
- `detect_anomalies(category)`  
- `compare_vendor_prices(vendor_df)`  

### ✔ Step 3: Build ADK Agent

- Register tools  
- Add instructions  
- Create `LlmAgent`  
- Enable session memory  

### ✔ Step 4: Run Interactive Tests

- Use `Runner` + `run_async()`  
- Validate tool calling  
- Test multi-step workflows  

---

## 🌐 Optional (Advanced)

### Deploy Agent to Vertex AI Agent Engine

- Serverless, scalable deployment  
- Real API endpoint  
- Supports memory bank  
- Ready for enterprise integration  

---

## 🛠 Installation (Local Use)

```bash
pip install google-adk
pip install pandas numpy
