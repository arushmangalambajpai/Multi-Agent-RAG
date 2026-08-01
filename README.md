# Multi-Agent RAG: Evaluating Collaborative Reasoning Architectures for Retrieval-Augmented Generation

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Gemini](https://img.shields.io/badge/LLM-Gemini_2.5_Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Research](https://img.shields.io/badge/Focus-Multi--Agent_RAG-8B0000?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-success?style=for-the-badge)

</p>

A research-oriented framework for **designing, executing, and evaluating multiple collaborative Retrieval-Augmented Generation (RAG) architectures** under challenging reasoning scenarios involving **conflicting evidence** and **refusal-aware question answering**.

Rather than comparing different language models, this project investigates **how different multi-agent orchestration strategies influence reasoning quality while using the same retrieval pipeline and the same LLM**.

---

## Overview

Retrieval-Augmented Generation systems often struggle when:

- Retrieved documents disagree with each other.
- Sources contain contradictory information.
- Evidence is incomplete or ambiguous.
- The correct behavior is to refuse answering instead of hallucinating.

This project explores whether **collaborative reasoning between specialized agents** can improve robustness compared to a traditional single-agent RAG pipeline.

The framework evaluates multiple reasoning architectures while keeping the retrieval mechanism and underlying language model fixed, allowing fair comparison of orchestration strategies.

---

## Key Features

- Multiple RAG reasoning architectures
- Modular agent-based design
- Parallel and sequential execution pipelines
- Conflict-aware evidence reasoning
- Refusal-aware answer generation
- Structured JSON communication between agents
- Automated benchmarking and evaluation
- Easily extensible architecture framework

---

# Supported Architectures

| Architecture | Description |
|-------------|-------------|
| **Single Agent** | Traditional RAG baseline using one reasoning agent. |
| **Sequential Pipeline** | Agents execute one after another while sharing an evolving reasoning state. |
| **Debate Architecture** | Multiple agents critique and refine candidate answers before synthesis. |
| **Parallel Pipeline** | Independent reasoning agents execute concurrently before aggregation. |
| **Parallel + Summarizer** | Parallel reasoning with an additional summarization stage prior to final synthesis. |

---

# System Workflow

```text
                     User Query
                          │
                          ▼
                Lexical Document Retrieval
                          │
                          ▼
               Selected RAG Architecture
                          │
        ┌──────────────┬──────────────┐
        │              │              │
   Specialized     Specialized    Specialized
      Agents          Agents         Agents
        │              │              │
        └──────────────┴──────────────┘
                          │
                          ▼
                 Final Synthesized Answer
                          │
                          ▼
                     Evaluation Metrics
```

---

# Repository Structure

```text
multi-agent-rag-master/
│
├── agents/                # Individual reasoning agents
├── architectures/         # Multi-agent execution strategies
├── evaluation/            # Benchmarking and scoring
├── prompts/               # Prompt templates
├── utils/                 # Shared utilities
├── data/                  # Evaluation datasets
│
├── main.py                # Main execution pipeline
├── run_eval.py            # Evaluation entry point
├── requirements.txt
└── README.md
```

---

# Agent Responsibilities

The framework consists of specialized agents responsible for different reasoning tasks.

| Agent | Responsibility |
|--------|----------------|
| Evidence Extractor | Extracts useful evidence from retrieved documents |
| Relevance Analyzer | Identifies information relevant to the query |
| Conflict Detector | Detects contradictions and inconsistencies |
| Critic | Reviews intermediate reasoning |
| Summarizer | Produces condensed evidence representations |
| Synthesizer | Generates the final grounded response |
| Refusal Judge | Determines whether answering is appropriate |

Each agent communicates using structured intermediate outputs, enabling modular and reusable reasoning pipelines.

---

# Evaluation Datasets

The repository includes datasets focused on:

- Conflicting information
- Contradictory evidence
- Refusal-required queries
- Grounded reasoning evaluation

These datasets are used to benchmark how different architectures respond under challenging retrieval conditions.

---

# Installation

Clone the repository

```bash
git clone https://github.com/<username>/multi-agent-rag.git
```

Navigate into the project

```bash
cd multi-agent-rag
```

Create a virtual environment

```bash
python -m venv venv
```

Activate it

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

Configure your API key

```text
Create a .env file and add:

GOOGLE_API_KEY=YOUR_API_KEY
```

---

# Running the Framework

Run a single experiment

```bash
python main.py
```

Run the evaluation pipeline

```bash
python run_eval.py
```

---

# Research Focus

This framework investigates the following research questions:

- Does multi-agent collaboration improve RAG performance?
- Can specialized agents better resolve conflicting evidence?
- Which orchestration strategy performs best under disagreement?
- How effectively can collaborative reasoning reduce hallucinations?
- When should a system refuse to answer instead of generating unsupported responses?

---

# Design Philosophy

The project intentionally keeps the retrieval component simple while emphasizing reasoning architecture.

- Fixed retrieval pipeline
- Fixed language model
- Variable reasoning architecture

This enables controlled comparison between orchestration strategies without introducing additional experimental variables.

---

# Technologies Used

- Python
- Google Gemini API
- JSON
- Concurrent Execution
- Retrieval-Augmented Generation (RAG)
- Prompt Engineering
- Multi-Agent Systems

---

# Future Improvements

Potential extensions include:

- Dense vector retrieval
- Hybrid lexical-semantic search
- BM25 integration
- FAISS or ChromaDB support
- LangGraph execution graphs
- Multi-LLM evaluation
- Human preference evaluation
- Citation verification
- Memory-enabled agents

---

# License

This project is released under the **MIT License**.

See the `LICENSE` file for additional information.

---

# Acknowledgements

This repository was developed as a research project exploring collaborative reasoning architectures for Retrieval-Augmented Generation systems.

The implementation demonstrates how modular agent design and orchestration strategies can be systematically evaluated for robust, evidence-grounded language model reasoning.

---

<p align="center">

**Multi-Agent RAG** • Collaborative Reasoning • Retrieval-Augmented Generation • AI Research

</p>