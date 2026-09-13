# Hi, I'm Sujeet Kumar Singh 👋

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Segoe+UI&weight=600&size=24&pause=2000&color=58A6FF&center=true&vCenter=true&width=700&lines=Azure+Data+Engineer;Databricks+%7C+Azure+Data+Factory;SQL+%7C+Python;Capital+Markets+%7C+Regulatory+Reporting" />
</p>

<p align="center">

  ![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
  ![Databricks](https://img.shields.io/badge/Databricks-EA4335?style=for-the-badge&logo=databricks&logoColor=white)
  ![ADF](https://img.shields.io/badge/Azure_Data_Factory-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
    ![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
  ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
  ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

</p>

**Data Engineer | Technical Business Analyst | Capital Markets & Regulatory Reporting**

📍 Bengaluru, India &nbsp;&nbsp;|&nbsp;&nbsp; 📧 sujeetsinghjsr@gmail.com &nbsp;&nbsp;|&nbsp;&nbsp; 🔗 [LinkedIn](https://www.linkedin.com/in/sujeetsinghjsr) &nbsp;&nbsp;|&nbsp;&nbsp; 💼 [Publicis Sapient](https://www.publicissapient.com)

---

## 🚀 About Me

I design and deliver **enterprise-scale data pipelines** for regulated industries —
capital markets, energy, and financial services.

- 🏗️ **Currently building** a MiFID II Regulatory Data Pipeline at Publicis Sapient
- 🌐 **Previously** led Shell's Data Mesh transformation at IBM
- 📊 **14+ years** across MiFID II · CFTC · BCBS 239 · G20 regulatory frameworks
- ⚙️ **Specialist in** pipeline architecture · trade linkage · delta check engines · data persistence

---

## 🏗️ Featured Project — MiFID II Regulatory Data Pipeline

> **Publicis Sapient** | Jan 2026 – Present

Building a production **Regulatory Data Pipeline (RDP)** for MiFID II ARM & APA reporting.
Translating Murex MX3 trade events into regulatory submissions via Kafka and AWS.

### Pipeline Flow
```
Murex MX3  →  De-Dup  →  MX Message Type Identifier  →  Trade Event Enricher
    →  GT Enrichment (LEI · MIC · IDM · EDM)
    →  JSON Data Products Creator  (35+ MxML → 1 flat JSON)
    →  JSON FX SWAP Aggregator  →  Post-Filter  →  ANNA Data Enricher
    →  [TRADE LINKAGE]  →  [DATA PERSISTENCE]
    →  Jurisdiction Eligibility  →  Outbound Reporting
    →  Aggregator / Delta Check (Phase A → B → C → D)
    →  ARM (batch)  +  APA (real-time)  →  Trade Repository
```

### Components I Designed & Delivered

#### 🔗 Trade Linkage Component (Built — July 2026)
- Designed **NB / CREATOR_NB waterfall lookup** replacing CONTRACT_ID approach
- Built replay detection using TRADE_REFERENCE + TMIT uniqueness check
- Designed DSL data extraction layer — XPaths in Excel on AWS S3, hot-reload on restart
- Handled PF / NPF / NRPT MiFID event categories and IS_NRPT propagation
- Produced: Jira ticket (AC, DoD, XPath details), draw.io flow, DSL rules file, UAT pack
- **Table:** `RDP_TRADE_DATA_LINKAGE` — TRADE_REF · CREATOR_TRADE_ID · MIFID_LINK_ID

#### 🗄️ Data Persistence Component (In Progress)
- Designed **two-table architecture** from Kear Chea (design authority) clarification call
- **Table 1:** `RDP_MIF_ELIGIBILITY_CACHE` — regime-agnostic · IDM + EDM only · cache layer
- **Table 2:** `RDP_MIFID_TRADE_DATA_PERSISTENCE` — MiFID-eligible trades only
- 8 DSL rules: SOFT_LINK (MIC F36, Venue ID F3) · CARRY_OVER (TRN F2, Trading Date F28,
  IDM F57, EDM F59) · DELTA_DRIVEN via Phase C write-back (Qty F30, DECR_INCR F32)

#### ✅ Delta Check Engine
- Phase A: polls persistence WHERE STATUS = PENDING
- Phase B: jurisdiction eligibility gate (IS_NRPT = Y → SUPPRESSED)
- Phase C: delta check on outbound table → write-back Qty + DECR_INCR + MIFID_ACTION
- Phase D: ARM/APA submission → MIFID_STATUS = COMPLETE
- MIFID_ACTION: NULL → NEWT / REPL / CANC

#### 📋 89-Scenario UAT Test Pack
- Dimensional coverage approach — 43 financial products × 21 event types
- Product × Event matrix eliminates combinatorial explosion
- P0 scenarios cover NEWT/REPL/CANC, NPF carry-forward, NRPT propagation, replay detection

**Tech stack:** Murex MX3 · Kafka · AWS S3 · DSL Framework · JSON · SQL · ARM/APA · MiFID II RTS 22

---

## 🌐 Previous Project — Shell Data Mesh Platform

> **IBM India embedded at Shell** | Aug 2022 – Oct 2025

Led Shell's enterprise **Data Mesh transformation** across global business units.

- Designed **Databricks Lakehouse** using Delta Lake · Parquet · ADLS Gen2
- Implemented **Unity Catalog + Collibra** for data governance · lineage · metadata
- Built data products on **Shell.ai** platform for engineers · analysts · data scientists
- Delivered **GDPR-compliant** data modernisation using CDC · batch · real-time streaming
- Led PoC initiatives validating capabilities before enterprise rollout

**Tech stack:** Databricks · PySpark · Apache Spark · Azure · AWS · Delta Lake · Parquet
· ADLS Gen2 · Unity Catalog · Collibra · Data Mesh · Data Products · CDC

---

## 📊 Previous Project — JPMorgan Reference Data Pipeline

> **JPMorgan Chase & Co** | Oct 2016 – Jul 2018

- Built ingestion and standardisation pipeline for **4M+ financial instruments**
- Bloomberg Data License + Python scripts → Global Instrument Master (GIM)
- **99% data integrity** for client golden source systems
- Handled corporate actions: splits · dividends · listings · delistings · ticker changes

**Tech stack:** Python · SQL · Bloomberg Data License · ISIN · LEI · Reference Data

---

## 🏦 Earlier Experience — Standard Chartered & S&P Global

**Standard Chartered Bank** (2018–2022) — Lead BA, Financial Markets Middle Office
- Led Murex migration (FEDS → Murex) — $3M cost savings · 35% processing improvement · 95% error reduction
- FX Spot · Forward · Swaps · NDF trade booking to risk systems

**S&P Global** (2012–2016) — BA, Real-time Market Data
- Market data direct feed products · daily quality alerts · corporate action reconciliation

---

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| **Data Engineering** | Databricks · PySpark · Apache Spark · Delta Lake · Parquet · CDC |
| **Cloud** | AWS (S3 · Cloud Practitioner certified) · Microsoft Azure (AZ-900 certified) |
| **Streaming** | Kafka · Event Mesh · Real-time Streaming · Batch Processing |
| **Storage / Format** | Delta Lake · ADLS Gen2 · JSON · MxML · XML · FpML · FIX Protocol |
| **Governance** | Unity Catalog · Collibra · Data Lineage · Metadata · Data Catalog |
| **Regulatory** | MiFID II ARM/APA RTS 22 · CFTC LTR · BCBS 239 · MiFIR · GDPR |
| **Domain Systems** | Murex MX3 · Bloomberg RHUB · Trax · OTCR · ANNA DSB · RDH/RDP |
| **Database** | SQL · Schema Design · DDL · Indexing · Data Quality · Reconciliation |
| **Frameworks** | Data Mesh · Data Products · Self-Serve Platforms · Agile Scrum |
| **Tools** | JIRA · Confluence · draw.io · Python · Excel (Dynamic Matrices) |

---

## 📁 Featured Repositories

| Repository | Description |
|---|---|
| [mifid-rdp-pipeline-design](https://github.com/sujeetsinghjsr/mifid-rdp-pipeline-design) | MiFID II RDP trade linkage and data persistence architecture |
| [data-mesh-shell](https://github.com/sujeetsinghjsr/data-mesh-shell) | Shell enterprise Data Mesh platform design patterns |
| [delta-check-engine](https://github.com/sujeetsinghjsr/delta-check-engine) | Delta check state machine for MiFID II regulatory reporting |
| [regulatory-uat-framework](https://github.com/sujeetsinghjsr/regulatory-uat-framework) | 89-scenario UAT test pack using dimensional coverage |
| [reference-data-pipeline](https://github.com/sujeetsinghjsr/reference-data-pipeline) | JPMorgan 4M+ instrument reference data pipeline |
| [databricks-lakehouse-patterns](https://github.com/sujeetsinghjsr/databricks-lakehouse-patterns) | Databricks Delta Lake patterns from Shell.ai platform |

---

## 📜 Certifications

- ☁️ **AWS Cloud Practitioner** — Amazon Web Services
- ☁️ **Microsoft Azure Fundamentals (AZ-900)**

---

## 📈 GitHub Stats

![Sujeet GitHub Stats](https://github-readme-stats.vercel.app/api?username=sujeethyd&show_icons=true&theme=tokyonight&hide_border=true&count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=sujeethyd&layout=compact&theme=tokyonight&hide_border=true)

---

*Open to Data Engineering roles — pipeline architecture · regulatory data · cloud data platforms*

📧 sujeetsinghjsr@gmail.com &nbsp; | &nbsp; 🔗 [LinkedIn](https://www.linkedin.com/in/sujeetsinghjsr)
