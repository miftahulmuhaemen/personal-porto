---
title: 'Software Engineer at Feedloop AI'
pubDate: '2022-12-01'
category: 'work'
techStack: ['TypeScript', 'NestJS', 'Node.js', 'Deno', 'Kubernetes', 'Google Cloud Platform', 'AWS Bedrock', 'Docker']
---

- [x] Multi-Cluster Production Infrastructure Maintained
- [x] Enterprise Document Intelligence Shipped to Production

::link{url="https://feedloop.ai/"}

## Overview & Role Summary

Feedloop AI develops enterprise low-code development platforms and applied generative AI systems for corporate digital transformation. As a Software Engineer (December 2022 – November 2024, Remote), primary responsibilities centered on three engineering pillars: developing client applications via Feedloop's proprietary Low-Code Development Platform (Qore), managing multi-cloud production Kubernetes clusters, and engineering an enterprise RAG (Retrieval-Augmented Generation) document intelligence backend.

## Architecture and Engineering Implementation

### 1. Enterprise Web Solutions via Low-Code Engine (Qore) & Serverless Edge

To satisfy enterprise client release cycles while ensuring custom business rule flexibility:

- **Platform Delivery**: Developed full-stack web platforms for 5 major client projects utilizing Feedloop's proprietary low-code engine (Qore). Accelerated time-to-market and feature delivery speeds by 30% compared to traditional greenfield web cycles.
- **Serverless Backend Extensions**: Engineered modular serverless cloud functions using Google Cloud Functions deployed with Node.js and Deno. These serverless modules handled custom business transactions, third-party authentication handshakes, HMAC-signed payment gateway webhooks, and data transformation adapters for legacy client systems.
- **Client State & API Integration**: Built responsive UI surfaces interacting with Qore REST/GraphQL backends, ensuring deterministic state caching and form validation across complex multi-step workflows.

### 2. Production Multi-Cluster Kubernetes Administration

Maintained container orchestration infrastructure ensuring high availability and predictable scaling across client workloads:

- **Cluster Management**: Administered 3 production-grade Kubernetes clusters distributed across Google Kubernetes Engine (GKE) and Microsoft Azure Kubernetes Service (AKS).
- **Deployment Hardening**: Formulated standardized Kubernetes resource manifests and Helm chart configurations, defining explicit resource limits (`requests`/`limits`), rolling deployment update strategies, and health-check probes (`livenessProbe`, `readinessProbe`).
- **Autoscaling & Resilience**: Implemented Horizontal Pod Autoscalers (HPA) configured against memory and CPU metrics to dynamically manage peak business-hour traffic. Reduced production downtime by 20% through automated pod recovery and zero-downtime rolling deployments.

### 3. Full-Stack RAG Document Intelligence Engine

Engineered an automated document intelligence backend designed to ingest, parse, and semantically query dense enterprise contracts and regulatory filings:

- **NestJS Modular Architecture**: Built a high-throughput backend service with NestJS and TypeScript following domain-driven design (controller, service, repository, and AI strategy modules).
- **Ingestion & Text Extraction Pipeline**: Processed complex multi-page legal documents (exceeding 100 pages per file) in PDF and scanned image formats. Pipeline executed document layout analysis, table extraction, and text normalization.
- **Semantic Chunking & Vector Search**: Implemented sliding-window text chunking with token overlap to preserve cross-sentence context, generating dense vector embeddings stored in a similarity index for sub-second retrieval.
- **Model Orchestration via AWS Bedrock**: Routed contextual prompts containing relevant retrieved passages to AWS Bedrock foundation models (Anthropic Claude and Amazon Titan) to extract structured entity schemas, contractual liabilities, and compliance clauses.
- **High-Availability Fallback Mechanism**: Integrated IBM Watson as an automated fallback provider. Middleware monitors AWS Bedrock response codes, latencies, and rate limits, instantly failing over to IBM Watson to guarantee continuous uptime for client legal teams.

## Measurable Engineering Outcomes

- **Delivery Velocity**: Increased delivery velocity by 30% across 5 enterprise client platforms using modular low-code components and custom cloud functions.
- **Cluster Stability**: Achieved a 20% reduction in production downtime across 3 GKE and AKS clusters through robust auto-scaling and proactive health monitoring.
- **AI Throughput**: Successfully parsed and enabled semantic questioning on 100+ page enterprise contracts with automated failover redundancy.
