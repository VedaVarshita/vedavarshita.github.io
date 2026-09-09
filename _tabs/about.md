---
# the default layout is 'page'
icon: fas fa-info-circle
order: 2
---

<!-- > Add Markdown syntax content to file `_tabs/about.md`{: .filepath } and it will show up on this page.
{: .prompt-tip } -->

I am a machine learning researcher and engineer. My research focuses on parts of deep learning that are still poorly understood — how networks should be initialized, how language models can be aligned to human preferences — and I pair it with the engineering to make those ideas run at scale, on real corpora, under production constraints.

I am currently a **Gen AI Researcher (contract) at BioNTech**, working on an agentic RAG and knowledge-graph system over a 3,285-document oncology corpus. That work spans a query-adaptive retrieval fusion strategy that weights vector, graph, and keyword signals by inferred query intent; a two-pass LLM entity extraction pipeline that builds a replayable knowledge graph of 18.5K entities and 82K+ edges on Amazon Neptune; and infrastructure tradeoff analysis that cut full-corpus LLM reprocessing cost by 98% ($15K → $300) through prompt-version-aware caching and automated cross-store integrity checks.

Before BioNTech, I was an **AI/ML Research Assistant at Drexel's CODED Lab** (July 2024 – December 2025), advised by Dr. Jake Williams. There I developed a Bayesian-inspired neural network initialization algorithm — using co-occurrence statistics and product quantization — that raised pre-gradient-update accuracy from roughly 10% to 74% on MNIST and 65% on CIFAR-10, validated by 75% cosine similarity between initialized and fully trained kernels. I also fine-tuned a 1.5B-parameter language model with preference-based DPO and RLHF on the HHH dataset, improving task performance by 17% and reducing perplexity by 20%.

I hold an **MS in Artificial Intelligence & Machine Learning from Drexel University** (GPA 3.9, 2023–2025). My path into ML started in industry at **Precisely** in Bangalore, where I productionized global location-intelligence data pipelines — expanding country coverage, building automated QA frameworks, and cutting processing time by 67% across 1M+ records. That mix of production data engineering and rigorous experimentation is what I bring to building intelligent systems that are both mathematically sound and deployable.