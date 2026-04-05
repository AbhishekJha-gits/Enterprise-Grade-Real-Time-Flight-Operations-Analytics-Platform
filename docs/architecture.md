project architecture
<img width="2912" height="1460" alt="Gemini_Generated_Image_nssnagnssnagnssn" src="https://github.com/user-attachments/assets/862151c9-12b9-4192-87b7-7999bfef172a" />

# System Architecture

## High-Level Overview

This platform implements a production-grade, near–real-time analytics architecture for operational data.

Data flows through clearly separated layers to ensure reliability, traceability, and business trust.

## Data Flow

Live Flight Data API
→ Bronze Layer (Raw Ingestion)
→ Silver Layer (Cleaned & Normalized)
→ Gold Layer (Business KPIs)
→ BI & Analytics Tools (Power BI)

## Layer Responsibilities

### Bronze Layer
- Stores raw API responses
- Preserves original source data
- Enables replayability and auditing
- Acts as the system of record

### Silver Layer
- Cleans and normalizes raw data
- Applies data quality checks
- Standardizes schemas
- Prepares data for analytics use

### Gold Layer
- Aggregates data into business KPIs
- Applies business logic centrally
- Produces analytics-ready tables
- Serves dashboards and reporting tools

## Orchestration

Apache Airflow orchestrates the full pipeline:
- Schedules ingestion and transformations
- Manages dependencies between layers
- Enables retries and safe reruns
- Provides observability and monitoring

## Design Principles
- Idempotent pipelines
- Incremental processing
- Clear ownership boundaries
- Analytics-first data modeling
