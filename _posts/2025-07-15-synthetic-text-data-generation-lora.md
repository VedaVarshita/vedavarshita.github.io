---
title: "Synthetic Text Data Generation Pipeline with LoRA"
date: 2025-07-15
categories: [Projects, Machine Learning]
tags: [pytorch, lora, llm, synthetic-data, mlflow, fastapi, docker, prefect]
---

## Overview

The Synthetic Text Data Generation Pipeline with LoRA is an end-to-end machine learning system designed to generate high-quality synthetic text data across multiple datasets. This project addresses the critical need for diverse training data in natural language processing tasks, particularly when working with limited or sensitive datasets.

## Problem Statement

Training robust language models often requires large, diverse datasets. However, acquiring such datasets can be challenging due to:
- Limited availability of domain-specific data
- Privacy concerns with sensitive information
- High costs associated with data collection and annotation
- Need for controlled data generation for specific use cases

This pipeline enables researchers and practitioners to generate synthetic text data that maintains the characteristics of real-world data while providing flexibility in generation modes (zero-shot, one-shot, and few-shot).

## Methodology

### Pipeline Architecture

The system implements a comprehensive four-stage pipeline:

1. **Data Ingestion**: Automated ingestion of source datasets (AG News and IMDB)
2. **Validation & Cleaning**: Data quality checks and preprocessing
3. **Monitoring**: Real-time tracking of generation metrics
4. **Generation**: Multi-mode text generation with optional LoRA fine-tuning

### Key Components

- **LoRA (Low-Rank Adaptation)**: Enables efficient fine-tuning of large language models by training only adapter weights, significantly reducing computational requirements
- **Prefect Orchestration**: Workflow management for reliable pipeline execution
- **Docker Containerization**: Ensures consistent environments across development and production
- **CI/CD Integration**: Automated testing and deployment
- **FastAPI RESTful APIs**: Exposes the pipeline as a service for integration into downstream systems

### Quality Metrics

The system tracks multiple quality and diversity metrics:
- **ROUGE-L**: Measures summary quality and coherence
- **Self-BLEU**: Evaluates diversity of generated text
- **N-gram Diversity**: Ensures variety in generated samples

## Results

- Successfully generated synthetic text data across AG News and IMDB datasets
- Enabled zero-shot, one-shot, and few-shot text generation modes
- Integrated comprehensive logging using MLflow for experiment tracking
- Achieved reproducibility across 10+ tunable hyperparameters
- Reduced computational costs through LoRA fine-tuning (training only adapter weights instead of full model)
- Processed 200+ synthetic samples per run with validated quality metrics

## Technologies Used

- **PyTorch**: Deep learning framework for model implementation
- **LoRA**: Low-rank adaptation for efficient fine-tuning
- **Prefect**: Workflow orchestration and scheduling
- **Docker**: Containerization for deployment
- **FastAPI**: RESTful API framework
- **MLflow**: Experiment tracking and model registry
- **CI/CD**: Continuous integration and deployment pipelines

## Repository

[GitHub Repository](https://github.com/VedaVarshita/Synthetic-text-data-generation)

## Future Work

- Extend support to additional datasets and domains
- Implement advanced diversity metrics (VendiScore)
- Optimize generation speed for real-time applications
- Add support for multi-modal synthetic data generation
