# 👋 Hi, I'm Ahmed

**Data Scientist & Analyst** building LLM-powered analytics tools that are measured, private and safe, with a focus on **Arabic / English** and **healthcare & operations** data.

---

## ⭐ Featured Project

### [Ask-the-Data · اسأل البيانات](https://github.com/A7mad8asim/ask-the-data)

A bilingual (Arabic / English, including Gulf dialect) **text-to-SQL assistant for clinic analytics**. Managers ask a question in their own words and get a correct number back, with a chart and the SQL that produced it.

- **79% execution accuracy** on a 100-question bilingual gold set, using a **local 8B model** (Qwen3 via Ollama), so no health data leaves the machine
- **20 / 20** privacy and safety attacks blocked: a SQL sandbox on the parsed query tree, a read-only database and small-group suppression (`<10`)
- The LLM never calculates a number: every figure in an answer is checked against the result table
- Ablation study (schema → glossary → few-shot retrieval → repair loop), a self-checking evaluation harness in CI, and Docker

`Python` `DuckDB` `sqlglot` `Ollama` `Claude API` `Streamlit` `pytest` `GitHub Actions` `Docker`

---

## 🛠 Tools I've Used in Public Projects

| Category | Tools |
| :--- | :--- |
| **Languages** | Python, SQL |
| **LLMs** | Ollama (Qwen3), Anthropic API, prompt design, few-shot retrieval, evaluation harnesses |
| **Data** | DuckDB, Pandas, NumPy, synthetic data generation |
| **Apps & Engineering** | Streamlit, Docker, pytest, GitHub Actions |

---

## 🎯 Currently Building

- 📚 Bilingual **RAG** over Arabic / English public documents, with citations and a retrieval benchmark
- 🧪 **Fine-tuning** a small open model to close the Gulf-dialect accuracy gap (63% → ?)
- 📈 **Forecasting** clinic demand and no-show risk with explainable ML

---

## 📫 Connect

- 📧 [a7mad8asim@gmail.com](mailto:a7mad8asim@gmail.com)
