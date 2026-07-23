# Executive Financial Intelligence Dashboard
## Corporate Development & Intrinsic Valuation Model (AAPL Case Study)

An enterprise-grade financial intelligence solution deployed via Power BI. This system bridges backwards-looking accounting records with a forward-looking predictive engine, leveraging Python linear regressions, interactive Discounted Cash Flow (DCF) frameworks, and native AI diagnostics.

---

### 📋 Project Ingestion & Data Engineering Pipeline
* **Data Sourcing:** Programmatically extracted raw historical accounting data (Income Statement, Balance Sheet, Cash Flow Statement) for Apple Inc. (AAPL) using the **FinancialModelingPrep.com API**.
* **Semantic Schema Mapping:** Engineered a clean, custom Star Schema from scratch by structuring a standardized `dAccountHead` dimensional table to unroll and unify disparate financial line items into a single, cohesive fact-table architecture.
* **Predictive Layer (VS Code):** Developed a standalone Python workflow (`.ipynb` notebook located in this repository) to run linear regression models on historical baseline periods, generating the discrete financial projections for the 2026–2030 valuation horizon.

---

### 🏛️ Core Architectural Features

#### 1. Executive Performance & Scenario Matrix ("C-Suite View")
* **Objective:** Compares multi-scenario operational performance (Actual vs. Budget vs. Forecast) over a fluid 10-year timeline.
* **Key Mechanisms:** Features a dynamic financial matrix driving an interactive Income Statement hierarchy alongside automated variance bridge waterfalls.
* **Dynamic UX Optimization:** Implements context-aware visual titles driven by a custom DAX text engine.

#### 2. Valuation & Strategic Planning ("Corporate Development View")
* **Objective:** Computes a fluid intrinsic Enterprise Value and Implied Share Price using a terminal-growth valuation engine.
* **Sensitivity Framework:** Integrates an interactive field parameter slider allowing executives to stress-test valuations across a 6% to 14% WACC matrix in real time.

#### 3. Capital Allocation & DCF Modeling ("Project ROI View")
* **Objective:** Prioritizes capital efficiency by plotting Project ROI against investment Payback Periods using a customized multi-layer coordinate plot.
* **Cash Horizon Visualization:** Contrasts nominal Free Cash Flows against present-value discounted equivalents to illustrate cash flow erosion over time.

#### 4. Automated AI Diagnostics & Deep-Dives
* **Objective:** Leverages native Power BI machine learning engines to automatically isolate and flag non-linear drivers of financial variances.
* **Key Mechanisms:** Maps discrete internal budget line variances against macroeconomic indicators via the *Key Influencers* visual. Includes an inline *Smart Narrative* component to auto-generate written variance commentary for executives.

---

### 🖥️ Dashboard Previews
Refer to the images/ folder  

---

### ⚡ Advanced Power BI Feature Implementation

#### 1. Visual Calculations & DAX Optimization
Optimized query performance by offloading simple visual-only logic from model-level measures into high-performance visual-layer calculations utilizing advanced windowing functions:
* **Running Total:** 
* **Moving Average:** 

#### 2. Advanced UX & Structural Layouts
* **Pop-Out Slicer Panel:** Built a collapsible filter pane using shape containers, grouped objects inside the Selection Pane, and decoupled Bookmarks ("Filter Panel Open" / "Filter Panel Close") to preserve report canvas real estate.
* **Report Page Tooltips:** Developed a micro-matrix tooltip detailing the structural breakdown of *Cash and cash equivlalents vs. Short Term Investments* linked natively to 'cashAndCashEquivalent' in Balance Sheet.
* **Chronological Fiscal Sorting:** Overrode alphabetical chart sorting bugs by mapping calendar string fields directly to the underlying `Fiscal Month Number` attribute.

---

### 🔐 Enterprise Architecture & Security (Proof of Concept)

#### 1. Row-Level Security (RLS)
Demonstrates data governance protocols by isolating financial visibility according to user permissions. Implemented a `Budget Viewer` role on the `dScenario` dimension table using the following expressive filter string:
```dax
[ScenarioName] IN {"Actual", "Budget"}
```
*Note: This automatically blinds unauthorized users from accessing proprietary Python forecasts or sensitive DCF calculations.*

#### 2. Hybrid Storage & Incremental Refresh
Configured a scalable data model framework using `RangeStart` and `RangeEnd` parameters in Power Query. Set up an Incremental Refresh Policy on the primary fact table (`fIncomeStatement`) to store static historical data (2020–2024) in Import Mode blocks, while keeping current periods responsive to real-time analysis.

*Architectural Note: In a live enterprise environment, this pattern is reserved for high-velocity transactional databases (10M+ rows). It is implemented here as an optimization proof-of-concept; standalone equity forecast models typically leverage standard Import Mode to ensure predictive Python regression elements run unimpeded.*
