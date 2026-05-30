# Hi 👋

Data Analytics Engineer with production experience across e-commerce, video streaming, and banking. 
I build end-to-end data pipelines — from API ingestion and SQL analytics to NLP models and cloud automation. 
Two of my projects have been published in peer-reviewed venues.

📧 revyakiner@gmail.com &nbsp;·&nbsp;
https://www.linkedin.com/in/egor-reviakin/

---

## 🧰 Tech Stack

| Area | Tools |
|---|---|
| **SQL** | AWS Athena (Presto/Trino), ClickHouse, Oracle SQL + OFSAA |
| **Cloud** | AWS Lambda, S3, Athena, Secrets Manager, CloudWatch, Amplify |
| **Python / Data** | pandas, AWS Wrangler, Parquet, OAuth 2.0, Docker |
| **APIs** | Amazon Ads API, Amazon SP-API, Google Sheets API, Telegram API, Notion API |
| **NLP / ML** | Transformers, BERT, scikit-learn, seqeval, pymorphy2, Hugging Face |

---

## 📊 Data Engineering & Analytics

### [SQL_Analytics_Portfolio](https://github.com/Sharik25/SQL_Analytics_Portfolio)
**Production SQL across three companies and three SQL engines**

Analytics queries from real roles — Amazon FBA e-commerce, video streaming, and banking — demonstrating breadth across domains, engines, and complexity levels.

| Engine | Dialect | Company | Domain |
|---|---|---|---|
| **AWS Athena** | Presto/Trino | Awegoo (Amazon FBA) | E-commerce P&L, inventory, marketing |
| **ClickHouse** | ClickHouse SQL | ivi.ru (Video Streaming) | Support analytics, contact rate |
| **Oracle SQL** | Oracle + OFSAA | GBC (Retail Bank) | Banking ETL, loan operations |

Highlights:
- **Master P&L engine** — full monthly P&L per ASIN combining 20+ revenue/cost components; multi-index CROSS JOIN spine, 10+ parallel LEFT JOINs, pre-pivoted 27-column fee transpose table
- **Inventory gap-fill** — LEAD/LAG nearest-neighbour gap-fill for sparse COGS time series, entirely in standard Presto SQL
- **FBA reimbursement finder** — date-range anti-JOIN to identify unclaimed destroyed inventory before Amazon's 18-month window closes
- **ClickHouse 7-day contact rate** — `arrayJoin(range(7))` sliding window with `uniq()` HLL, dictionary joins, and `argMax` for mutable ticket state
- **Banking ETL** — 5-CTE pipeline with LAG-derived migration window boundaries, time-valid joins, Oracle DB links across production OFSAA schema

`AWS Athena` `ClickHouse` `Oracle SQL` `Presto/Trino` `Window Functions` `CTEs` `ETL`

---

### [Python_AWS_Automation_Portfolio](https://github.com/Sharik25/Python_AWS_Automation_Portfolio)
**7 production automation pipelines on AWS for Amazon e-commerce**

Python-based systems automating reporting, data ingestion, and operational workflows — all running as scheduled or event-driven AWS Lambda functions.

| # | Project | Key techniques |
|---|---|---|
| 1 | **Amazon Ads Marketing Models** | Athena SQL → ACOS/ROAS/CTR/CPC → Google Sheets (multi-brand, multi-region) |
| 2 | **Amazon Ads ETL (US + CA)** | Full async report lifecycle: OAuth → poll → GZIP JSON → S3 Parquet |
| 3 | **FBA Inventory Planning** | 3-level nested Athena SQL with ROW_NUMBER(), inventory age buckets × COGS |
| 4 | **Dynamic Athena View Builder** | Runtime column discovery → `CREATE OR REPLACE VIEW` with `map_agg` pivot |
| 5 | **FBA Shipment Statuses Snapshot** | SP-API pagination across 10 statuses → 30-field DataFrame → daily Parquet |
| 6 | **Sales Analysis Report** | Athena → Google Sheets with programmatic conditional formatting rules |
| 7 | **Lambda Error Notification Tool** | CloudWatch Logs → base64/GZIP decode → Google Sheets error dashboard |

`Python` `AWS Lambda` `AWS Athena` `AWS S3` `AWS Secrets Manager` `Docker` `Amazon Ads API` `Amazon SP-API` `Google Sheets API` `OAuth 2.0` `Parquet`

---

## 🔬 NLP & Applied Research

### [RANLP_2023](https://github.com/Sharik25/RANLP_2023)
**Binary text classification of Russian-language Telegram posts**
*Published at [RANLP 2023](https://aclanthology.org/2023.ranlp-1.123) — Recent Advances in Natural Language Processing*

Fine-tuned multilingual BERT to classify Telegram channels as state-aligned vs. independent media. Dataset of ~11 300 posts collected via Telegram API over 12 months, labeled automatically from external authoritative registries.

- **Accuracy:** 96.3% in-distribution · 92.2% out-of-distribution
- Outperforms all baselines: Logistic Regression, Random Forest, XGBoost over tf-idf
- Model and datasets published on 🤗 Hugging Face

`Python` `Transformers` `BERT` `Text Classification` `Telegram API` `scikit-learn` `Hugging Face`

---

### [World_Scientific_Book_Chapter_2025](https://github.com/Sharik25/World_Scientific_Book_Chapter_2025)
**NLP pipeline: NER + classification + geospatial visualisation**
*Published in [Detecting Online Propaganda and Misinformation](https://books.google.com/books?id=VYx5EQAAQBAJ&pg=PA185), World Scientific, 2025, p. 185*

Two-stage pipeline combining the RANLP classifier with a fine-tuned NER model (BIO scheme, 9 labels) to extract structured event data — damage triggers, effects, regions, cities — then geocode and render results as interactive maps. Handles Russian morphology via `pymorphy2` for high-recall location matching.

```
Raw post → BERT classifier  → editorial stance + confidence
         → BERT NER (BIO)   → trigger / effect / region / city
         → Nominatim         → lat/lon → interactive map
```

`Python` `NER` `Token Classification` `pymorphy2` `Geocoding` `LightTag` `Hugging Face`

---

## 🛠 Tools & Applications

### [Notion_Task_Manager_Telegram_Bot](https://github.com/Sharik25/Notion_Task_Manager_Telegram_Bot)
**Telegram bot integrated with Notion API** · *Human-Computer Interfaces course, SCE*

Python/Flask application connecting Notion and Telegram Bot APIs via webhooks for in-messenger task management.

`Python` `Flask` `Notion API` `Telegram Bot API` `Webhooks`
