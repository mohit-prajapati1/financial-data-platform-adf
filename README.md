# financial-data-platform-adf
# 🏦 APEX FINANCIAL SERVICES

## SQL Server → Azure Data Lake Storage Gen2

Production-oriented data engineering project demonstrating the ingestion of data from an on-premises SQL Server database into **Azure Data Lake Storage Gen2 (ADLS Gen2)** using **Azure Data Factory (ADF)** and **Self-Hosted Integration Runtime (SHIR)**.

---

## 🏗️ Overall Architecture

![Overall Architecture](architecture/01-overall-architecture.png)

```text
                         APEX FINANCIAL SERVICES
                                  │
                                  ▼
                    ┌──────────────────────────┐
                    │       SQL SERVER         │
                    │      ApexCoreBanking     │
                    │                          │
                    │  Branch                  │
                    │  Customer                │
                    │  Account                 │
                    │  Loan                    │
                    │  Transaction             │
                    │  Payment                 │
                    └────────────┬─────────────┘
                                 │
                                 │ On-Premise
                                 │ Connectivity
                                 ▼
                    ┌──────────────────────────┐
                    │    SELF-HOSTED IR        │
                    │                          │
                    │ Secure Connectivity      │
                    │ between SQL & Azure      │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │    AZURE DATA FACTORY    │
                    │                          │
                    │ Metadata Control         │
                    │ Pipeline Execution       │
                    │ Dynamic Processing       │
                    │ Error Handling           │
                    │ Audit Logging            │
                    │ Monitoring               │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │        ADLS GEN2         │
                    │                          │
                    │          RAW             │
                    │                          │
                    │ Branch                   │
                    │ Customer                 │
                    │ Account                  │
                    │ Loan                     │
                    │ Transaction              │
                    │ Payment                  │
                    └──────────────────────────┘
