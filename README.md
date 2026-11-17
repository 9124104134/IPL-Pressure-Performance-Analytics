# 🏏 IPL Pressure Performance Analytics

### Identifying Reliable Batters and Bowlers Under Pressure | IPL 2022–2026

## 📌 Project Overview

This project focuses on identifying reliable IPL batters and bowlers who perform effectively in high-pressure match situations.

Developed as part of the **Rajasthan Royals – SupeRR Selector Season 2 challenge**, the analysis uses IPL ball-by-ball data from 2022 to 2026 to evaluate player performance beyond conventional cricket statistics.

The project applies data preprocessing, pressure-situation identification, performance metrics and weighted reliability scoring to generate separate Top 10 rankings for batters and bowlers.

## 🎯 Objectives

- Identify high-pressure situations in IPL matches.
- Analyse batting and bowling performance under pressure.
- Evaluate player reliability using multiple performance indicators.
- Develop weighted scoring models to rank players.
- Test ranking stability using different eligibility thresholds and scoring weights.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data analysis and processing |
| Pandas | Data cleaning and manipulation |
| NumPy | Numerical computations |
| Google Colab | Development environment |
| Matplotlib / Seaborn | Data visualization, where applicable |

## 📊 Dataset

The analysis uses IPL data covering five seasons:

- IPL 2022
- IPL 2023
- IPL 2024
- IPL 2025
- IPL 2026

**Dataset overview:**
- 371 IPL matches in the competition records.
- 87,687 IPL ball-by-ball records.
- 367 matches with available ball-by-ball data.
- Four abandoned matches without ball-by-ball data.

The original dataset is not included in this repository. Please refer to the challenge-provided data pack for the source data.

## 🔍 Methodology

### 1. Data Preparation

- Loaded and explored the supplied CSV datasets.
- Cleaned and prepared ball-by-ball records.
- Focused on regular first and second innings.
- Excluded short super-over-type innings from regular innings analysis.
- Processed delivery and extras information for batting and bowling calculations.

### 2. Identifying High-Pressure Situations

Second-innings chase deliveries were evaluated using:

- Required run rate.
- Wickets lost.

A composite pressure score was calculated:

**Pressure Score = 100 × (0.50 × RRR Percentile + 0.50 × Wickets-Lost Percentile)**

The top 10% of deliveries by this composite score were classified as high-pressure deliveries.

### 3. Batting Performance Analysis

Batters were evaluated using:

| Metric | Weight |
|---|---:|
| Strike Rate | 30% |
| Boundary Rate | 15% |
| Dot-Ball Avoidance | 15% |
| Dismissal Avoidance | 20% |
| Match Consistency | 20% |

### 4. Bowling Performance Analysis

Bowlers were evaluated using:

| Metric | Weight |
|---|---:|
| Economy Rate | 25% |
| Wickets per 100 Legal Balls | 25% |
| Dot-Ball Rate | 20% |
| Boundary Prevention | 15% |
| Match Consistency | 15% |

Metrics were converted into percentile-based scores, with lower-is-better metrics appropriately reversed.

### 5. Eligibility Criteria

The primary leaderboard uses the following minimum exposure requirements:

- **Batters:** At least 50 pressure balls faced across at least 5 matches.
- **Bowlers:** At least 50 legal pressure balls bowled across at least 5 matches.

### 6. Sensitivity Analysis

Different sample-size thresholds and scoring-weight combinations were tested to examine whether the rankings remained stable under alternative assumptions.

## 🏆 Final Outputs

The analysis produces two separate leaderboards:

**Top 10 Batters**
- Pressure balls faced
- Matches
- Runs scored
- Strike rate
- Boundary rate
- Dot-ball rate
- Dismissal rate
- Reliability score

**Top 10 Bowlers**
- Legal pressure balls
- Matches
- Wickets
- Economy rate
- Wickets per 100 legal balls
- Dot-ball rate
- Boundary rate
- Consistency rate
- Reliability score

## 📁 Repository Structure

```text
IPL-Pressure-Performance-Analytics/
│
├── README.md
│
├── notebooks/
│   └── IPL_Pressure_Analysis.ipynb
│
├── outputs/
│   ├── final_batting_top10.csv
│   └── final_bowling_top10.csv
│
└── reports/
    └── RR_SupeRR_Selector_Pressure_Reliability_Report.pdf
```

## 📄 Project Report

The detailed methodology and findings are available in:

`reports/RR_SupeRR_Selector_Pressure_Reliability_Report.pdf`

## ⚠️ Limitations

- Pressure is defined using second-innings chase situations and may not capture every form of match pressure.
- Players have different levels of exposure to high-pressure deliveries.
- Minimum sample-size thresholds can affect player eligibility.
- Weighted scores depend on the selected metrics and weights.
- Historical performance does not guarantee future performance.

The rankings should therefore be interpreted within the defined analytical framework rather than as absolute measures of player ability.

## 💡 Key Learning Outcomes

- Practical experience with real-world cricket datasets.
- Data cleaning and exploratory data analysis.
- Feature engineering and performance metric development.
- Percentile-based scoring and player ranking.
- Sensitivity analysis and evidence-based interpretation.
- Communicating analytical findings through structured reports.

## 👩‍💻 Project Context

**Challenge:** Rajasthan Royals – SupeRR Selector Season 2  
**Focus Area:** IPL Player Performance Analytics  
**Analysis Period:** IPL 2022–2026  
**Tools:** Python, Pandas, NumPy and Google Colab

---

*An analytical approach to understanding which players deliver when the pressure is highest.*
