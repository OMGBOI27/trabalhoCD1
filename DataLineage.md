graph TD
    subgraph "1. Raw Sources (CSV)"
        A[incidents_master.csv] --> D{Merge/Join}
        B[financial_impact.csv] --> D
        C[market_impact.csv] --> D
    end

    subgraph "2. Bronze Layer (Parquet)"
        D --> E[incidents_raw.parquet]
        E --- F[+ Ingestion Metadata]
        E --- G[+ Snake Case Columns]
    end

    subgraph "3. Silver Layer (ML-Ready)"
        E --> H[incidents_silver.parquet]
        H --- I[Data Cleaning]
        H --- J[Financial Imputation]
        H --- K[Feature: high_impact_label]
    end

    subgraph "4. Consumers"
        H --> L[Exploratory Data Analysis]
        H --> M[Machine Learning Models]
    end
