---
# the default layout is 'page'
icon: fas fa-project-diagram
order: 3
---

# Research

**Bayesian Neural Network Initialization** | CODED Lab, Drexel University | PyTorch

A novel warm-start algorithm that initializes network weights from co-occurrence statistics and product quantization instead of random sampling.

- Raised pre-gradient-update accuracy from ≈10% (random) to **74% on MNIST** and **65% on CIFAR-10**
- **75% cosine similarity** between initialized and fully trained kernels, confirming an informative warm start

**LLM Alignment with DPO / RLHF** | CODED Lab, Drexel University | PyTorch

Preference-based fine-tuning of a 1.5B-parameter language model on Anthropic's HHH dataset.

- **+17%** task performance, **−20% perplexity** (31.64 → 25.42)
- Aligned, coherent outputs following Responsible AI practices

# Projects

**LLaMA Vector Search Engine** | LangChain · LLaMA 3.2 · FAISS · DSPy · LangGraph

[Writeup](/posts/llama-vector-search-engine/) · [Code](https://github.com/VedaVarshita/llama3.2_RAG_Application)

A local, modular RAG research assistant over 30+ ML papers with three retrieval modes (standard, LangGraph workflow, DSPy-optimized).

- **86% MRR**, **56%** search-latency reduction
- DSPy + MMR retrieval: **+27%** answer relevance, 1.06s generation latency
- Stateful LangGraph workflow: **94%** query success via conditional routing and document grading

**Synthetic Text Data Generation Pipeline with LoRA** | PyTorch · LoRA · Prefect · Docker · FastAPI · MLflow

[Writeup](/posts/synthetic-text-data-generation-lora/) · [Code](https://github.com/VedaVarshita/Synthetic-text-data-generation)

A 4-stage synthetic-data pipeline (zero / one / few-shot + LoRA fine-tuning) with orchestration, containerization, and API serving.

- Perplexity reduced **10–15×**, validated with ROUGE-L, Self-BLEU, and VendiScore
- Reproducible across 10+ tunable hyperparameters; trains adapter weights only

**Research Hub** | arXiv & Semantic Scholar APIs · Cloudflare Workers

[Open the tool](/research-hub/)

A literature-management tool I built for my own workflow — fetches papers from arXiv and Semantic Scholar and organizes them into a structured knowledge base.

**Air Quality Forecasting** | Python · statsmodels · ARIMA / SARIMA

[Writeup](/posts/predictive-modeling-daily-air-quality-time-series/) · [Code](https://github.com/VedaVarshita/Predictive-Modeling-of-Daily-Air-Quality-Using-Time-Series)

Daily air-quality forecasting with rigorous stationarity analysis, smoothing, and classical time-series models.

- **~20–30% RMSE reduction** vs naive baselines through proper preprocessing and stationarity handling
- ADF testing, ACF/PACF-guided ARIMA order selection, time-aware validation
