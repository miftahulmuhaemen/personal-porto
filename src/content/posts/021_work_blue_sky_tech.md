---
title: 'Data and Backend Engineer at Blue Sky Tech (Bythen AI)'
pubDate: '2025-03-01'
category: 'work'
techStack:
  ['Go', 'Python', 'Apache Airflow', 'Metabase', 'Great Expectations', 'Google Cloud Platform', 'GCP Pub/Sub', 'Docker']
---

- [x] Production System in Active Operation
- [x] Scaled Data Pipelines to Millions of Daily Records

::link{url="https://bythen.ai/"}

## Overview & Role Summary

Blue Sky Tech (operating Bythen AI) builds generative AI products for digital avatars and autonomous video creation. During this tenure as Data and Backend Engineer (March 2025 – June 2026, Remote), the primary mandate spanned two core technical domains: architecting the company's foundational analytical data warehouse and developing backend microservices powering the Bythen AI Video Producer.

The primary engineering challenges involved handling asynchronous generative workloads, consolidating fragmented telemetry from disparate microservices into an auditable data repository, and enforcing strict data quality standards before metric visualization.

## Architecture and Engineering Implementation

### 1. Foundational Data Warehouse & ETL Orchestration

Prior to this implementation, application telemetry and generation events were siloed across independent operational databases, restricting cross-functional visibility into user conversion, rendering latencies, and token burn rates:

- **Warehouse Data Modeling**: Architected an analytical data store utilizing dimensional modeling (star schema) with centralized fact tables for generation runs (`fact_video_generations`, `fact_user_sessions`) linked to conformance dimensions (`dim_users`, `dim_plans`, `dim_templates`).
- **Apache Airflow DAG Pipelines**: Authored automated Directed Acyclic Graphs (DAGs) in Python orchestrating scheduled hourly and daily batch extraction from production MongoDB and PostgreSQL datastores into the data warehouse.
- **Data Quality Contracts with Great Expectations**: Embedded automated validation assertions within intermediate pipeline stages. Airflow workers validate non-null constraints, foreign key referential integrity, schema conformity, and value distribution bounds prior to loading. Pipeline runs automatically halt and trigger alerting upon contract violation, preventing corrupt analytics.

### 2. Core Go Microservices for AI Video Producer

The Bythen AI Video Producer provides an end-to-end storyboard editor that generates animated avatar scenes from structured user prompts:

- **Go Ingestion and Orchestration**: Built high-concurrency backend services in Go 1.22 using standard library concurrency primitives (goroutines, worker pools, channels) to handle incoming user storyboard generation requests.
- **Asynchronous Task Queue via GCP Pub/Sub**: Decoupled HTTP API endpoints from long-running GPU inference clusters. Incoming scene creation requests are validated, written to an operational log, and published to Google Cloud Pub/Sub topics consumed by distributed render workers.
- **Webhook Ingestion**: Implemented webhook handlers to process asynchronous GPU cluster callbacks, safely recording generation completion, scene transition frames, and artifact URLs with idempotent deduplication keys.

### 3. Session Enrichment & Telemetry Resolution

- **Event Enrichment Worker**: Developed a stream-processing service that intercepts raw frontend user interactions and binds them to persistent session lifecycles, user-agent parsing models, and geographical IP lookups.
- **Data Consistency**: Ensured analytics pipelines capture end-to-end user journeys from initial template selection to final MP4 download without dropping events during network degradation.

### 4. BI Visualization with Metabase

- **Executive & Product Dashboards**: Designed and tuned Metabase analytical dashboards querying millions of records with pre-aggregated summary views and materializations.
- **Key Metric Tracking**: Delivered real-time visibility into generation queue depth, average render duration per model, daily active creators (DAC), retention funnels, and infrastructure compute cost per minute of rendered video.

## Measurable Engineering Outcomes

- **Scale**: Pipelined and aggregated millions of raw operational events into a structured analytical warehouse daily.
- **Data Quality**: Eliminated silent downstream metric discrepancies through automated Great Expectations verification steps in Airflow.
- **System Decoupling**: Reduced API gateway latency by transitioning generative rendering tasks to asynchronous GCP Pub/Sub event-driven pipelines.
