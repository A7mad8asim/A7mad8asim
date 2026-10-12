# 👋 Hi, I'm Ahmed

**Data Scientist & Analyst** building LLM-powered analytics tools that are measured, private and safe, with a focus on **Arabic / English** and **healthcare & operations** data.

---

## ⭐ Featured Projects

### [Ask-the-Data · اسأل البيانات](https://github.com/A7mad8asim/ask-the-data-text-to-sql)

A bilingual (Arabic / English, including Gulf dialect) **text-to-SQL assistant for clinic analytics**. Managers ask a question in their own words and get a correct number back, with a chart and the SQL that produced it.

- **79% execution accuracy** on a 100-question bilingual gold set, using a **local 8B model** (Qwen3 via Ollama), so no health data leaves the machine
- **20 / 20** privacy and safety attacks blocked: a SQL sandbox on the parsed query tree, a read-only database and small-group suppression (`<10`)
- The LLM never calculates a number: every figure in an answer is checked against the result table
- Ablation study (schema → glossary → few-shot retrieval → repair loop), a self-checking evaluation harness in CI, and Docker

`Python` `DuckDB` `sqlglot` `Ollama` `Claude API` `Streamlit` `pytest` `GitHub Actions` `Docker`

### [Arabic RAG Assistant · مساعد الإحصاءات](https://github.com/A7mad8asim/arabic-rag-assistant) <sub>work in progress</sub>

Bilingual **retrieval-augmented generation over Qatar's official open statistics**: 1,432 National Planning Council datasets from the Qatar Open Data portal. Ask in Arabic or English; every figure in the answer links to the dataset it came from.

- **Grounding check:** the model may only repeat numbers found in the sources it cites; any other number and the answer is withheld
- **Bilingual chunks:** Arabic and English values are paired from the portal's twin columns (`Doha / الدوحة`), so one index serves both languages
- **81–83% of questions on two held-out sets answered correctly on a local 8B model, at about 2 seconds per question**; every unanswerable question refused, about 1 lookup in 25 wrong (168 bilingual gold questions: dev, two held-out splits and a large-table split)
- **Ablation, step by step:** reranking moved the answer row to first place (57% → 80%), showing the model only the 3 best rows fixed refusals, and query translation plus hybrid BM25 + bge-m3 retrieval recovered Gulf dialect; profiling then found a 2-second `localhost` delay per request and cut the time per question from 12.4 to 2.2 seconds
- **All 1,432 datasets indexed:** 2.8 million trade rows as server-side totals by country and month, the rest in full (29,699 chunks); a Streamlit app with linked source cards, a GPU Docker setup tested end to end, and tests in CI

`Python` `RAG` `BM25` `bge-m3` `Ollama` `Streamlit` `REST API` `Docker` `pytest` `GitHub Actions`

### [Gulf-Dialect Rewriter · من اللهجة إلى الفصحى](https://github.com/A7mad8asim/gulf-dialect-rewriter) <sub>work in progress</sub>

A **QLoRA fine-tuned Qwen3-1.7B** that rewrites Gulf-dialect Arabic questions into Modern Standard Arabic before they reach the Ask-the-Data text-to-SQL assistant, to close its dialect gap.

- **Fresh dialect questions answered correctly: 44% → 60%** with the rewriter in front (a hand-written MSA version reaches 76%); Ask-the-Data's own dialect questions 57.9% → 68.4%. It also hurts questions already in MSA (77% → 68%), so it belongs behind a dialect check: routed that way, all 50 Arabic questions go from 70% to 74%
- **Guardrail in code:** a rewrite may change wording, never content; one that drops or adds a number or Latin term is discarded and the original question is used
- **Data:** human-verified Gulf ↔ MSA tweets and Saudi translations, plus a seeded generator of clinic questions in Gulf dialect (33 measures); every pair checked for leakage against the test questions, which also found 220 training tweets repeating the corpus's own test set
- **Honest measurement:** paired runs against a prompted 8B baseline and an MSA ceiling; the first model (40% on the fresh set) showed it had learned the generator's templates, which led to the expanded generator
- Trained in 4-bit on one RTX 5060 Ti (16 GB) with transformers and PEFT; tests in CI

`Python` `PyTorch` `Hugging Face Transformers` `PEFT / QLoRA` `bitsandbytes` `Ollama` `pytest` `GitHub Actions`

---

## 🛠 Tools I've Used in Public Projects

| Category | Tools |
| :--- | :--- |
| **Languages** | Python, SQL |
| **LLMs** | Ollama (Qwen3), Anthropic API, prompt design, few-shot retrieval, evaluation harnesses |
| **Fine-tuning** | PyTorch, Hugging Face Transformers, PEFT (LoRA / QLoRA), bitsandbytes 4-bit quantization, training-data leakage checks |
| **Retrieval / RAG** | BM25, bge-m3 embeddings, hybrid retrieval with reciprocal rank fusion, LLM reranking, query translation, Arabic text normalization, citation grounding |
| **Data** | DuckDB, Pandas, NumPy, REST API ingestion, synthetic data generation |
| **Apps & Engineering** | Streamlit, Docker, pytest, GitHub Actions |

---

## 🎯 Currently Building

- 📚 The **RAG** assistant's last wrong answers: a model row check and a code-based sub-group check cut wrong figures from 16 to 6 on the same answers; the rest are wrong measures or near-identical tables
- 🧪 The **Gulf-dialect rewriter**: a new held-out test set written without looking at the training generator, and a check that catches rewrites that swap clinic terms
- 📈 **Forecasting** clinic demand and no-show risk with explainable ML

---

## 📫 Connect

- 📧 [a7mad8asim@gmail.com](mailto:a7mad8asim@gmail.com)
