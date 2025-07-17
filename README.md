<div align="center">

# 🤖 PitchCraft AI 📈

**Automated Pitch Book & Investment Report Generator**

</div>

<p align="center">
  <a href="#-about-the-project">About</a> •
  <a href="#-how-it-works">Workflow</a> •
  <a href="#-the-agent-team">The Agents</a> •
  <a href="#-getting-started">Getting Started</a>
</p>

<p align="center">
    <img src="https://img.shields.io/badge/status-in%20development-orange" alt="Status">
    <img src="https://img.shields.io/badge/version-1.0.0-blue" alt="Version">
    <img src="https://img.shields.io/badge/license-MIT-brightgreen" alt="License">
</p>

---

## 🎯 About The Project

> PitchCraft AI is a sophisticated multi-agent system designed to fully automate the creation of comprehensive pitch books and investment reports. It orchestrates a team of specialized AI agents, transforming raw financial data and user requests into a polished, professional, and data-driven document with zero manual intervention.

### ✨ Key Features:

-   **Fully Automated**: From initial request to final report delivery, the process is hands-off.
-   **Modular by Design**: Each agent has a single, well-defined responsibility, making the system robust and easy to extend.
-   **Data-Driven**: Integrates with live financial data sources to provide up-to-date analysis.
-   **Consistent & Professional**: Ensures all reports are generated in a standardized, high-quality format.

---

## ⚙️ How It Works

The system is managed by a root **`Pitch_book_agent`** which acts as a project manager. It directs a sequence of specialized sub-agents to gather data, perform analysis, and assemble the final report.

```mermaid
graph TD
    style User fill:#5DADE2,stroke:#333,stroke-width:2px,color:#fff
    style Manager fill:#8E44AD,stroke:#333,stroke-width:2px,color:#fff
    style Data fill:#1ABC9C,stroke:#333,stroke-width:2px,color:#fff
    style Analysis fill:#F39C12,stroke:#333,stroke-width:2px,color:#fff
    style Assembly fill:#E74C3C,stroke:#333,stroke-width:2px,color:#fff
    style Report fill:#2ECC71,stroke:#333,stroke-width:2px,color:#fff

    User(👤 User Request) --> Manager(🤖 Pitch_book_agent);

    subgraph "Phase 1: Data Gathering"
        Manager --> Data1(📡 DMIS_Agent);
        Manager --> Data2(📊 FMPS_Agent);
    end

    subgraph "Phase 2: Analysis & Narrative"
        Data1 -- News & Market Data --> Analysis(✍️ CGNS_Agent);
        Data2 -- Quantitative Data --> Analysis;
    end
    
    subgraph "Phase 3: Final Assembly"
        Analysis -- Investment Summary --> Assembly(📑 DVS_Agent);
        Data1 -- Raw Data --> Assembly;
        Data2 -- Raw Data --> Assembly;
    end

    Assembly --> Report(✅ Final Report.pdf);

    classDef default font-family: 'Helvetica', sans-serif;
