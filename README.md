# Will AI Take Your Job? Analyzing Layoff Risk in the AI Era

**A Python/Pandas exploratory data analysis of AI-driven layoff risk across industries, job roles, and career factors.**

## Problem Statement

As AI adoption accelerates across industries, which workers are actually most exposed to layoff risk — and is that risk driven more by *what a job involves*, or by *how aggressively a company has adopted AI*? This project analyzes 20,000 employee records spanning 8 industries to answer that question, using pandas for data manipulation and seaborn/matplotlib for visualization.

## Dataset

- **20,000 rows**, 16 columns
- Covers 8 industries (Manufacturing, Retail, Logistics, Finance, Telecom, IT, Healthcare, Education)
- Job characteristics: Routine_Task_Percentage, Creativity_Requirement, Human_Interaction_Level, Job_Level, Education_Level
- AI-related features: AI_Adoption_Level, Number_of_AI_Tools_Used, AI_Usage_Hours_Per_Week, Tasks_Automated_Percentage, AI_Training_Hours
- Target variable: `Layoff_Risk` (Low / Medium / High)

## Key Findings

1. **Layoff risk is roughly evenly split** across the workforce — 34.0% High, 33.0% Medium, 33.0% Low.
2. **Manufacturing carries the highest layoff risk at 48.2%**, followed by Logistics (41.5%) and Retail (40.7%). Education (20.1%) and Healthcare (20.8%) are the safest.
3. **Routine and automatable work is the clearest driver of risk.** Median Routine_Task_Percentage rises from approx. 25% (Low risk) to approx. 50% (Medium) to approx. 77% (High) — a clean staircase pattern, mirrored by Tasks_Automated_Percentage.
4. **Company AI adoption level dramatically amplifies risk.** Only approx. 9% of employees at Low-AI-adoption companies are High risk, versus approx. 81% at High-AI-adoption companies.
5. **Education and seniority both act as protective factors.** High-risk share drops from 45.6% (High School) to 20.1% (PhD), and from 44.5% (Entry-level) to 11.5% (Senior). Interestingly, **AI training hours do *not* show the same protective pattern** — High-risk employees receive the *most* training (median approx. 17 hrs) versus Low-risk employees (median approx. 5 hrs), suggesting training is deployed reactively to already-automating roles rather than proactively preventing risk.
6. **Job role rankings sharpen the picture.** Operator (50.2%), Production Supervisor (48.3%), and Quality Engineer (46.0%) face the highest risk; Teacher (16.4%), Nurse (16.7%), and Research Assistant (21.0%) face the lowest. Technical/analytical roles like Data Analyst (28.3%), Software Engineer (28.1%), and ML Engineer (27.5%) sit meaningfully lower than production roles, but not risk-free.
7. **Routine task content and creativity are near-mirror opposites** (correlation −0.93), while Routine_Task_Percentage and Tasks_Automated_Percentage move together strongly (+0.89). Demographic factors (Age, Experience) show almost no relationship with AI exposure — job content matters far more than who's doing the job.

## Visualizations

| Chart | Insight |
|---|---|
| Layoff Risk Distribution | Overall workforce risk split |
| Risk by Industry | Manufacturing/Logistics/Retail most exposed |
| Routine Task % & Automation % by Risk | Task content drives risk |
| Risk by AI Adoption Level | Organizational AI strategy compounds risk |
| Risk by Education Level | Education as a protective factor |
| Creativity & AI Training Hours by Risk | Training is reactive, not protective |
| Risk by Seniority | Seniority as a protective factor |
| High-Risk Share by Job Role | Role-level ranking, most/least exposed |
| Correlation Matrix | Relationships between numeric features |

## Tools Used

- **Python** — pandas, numpy
- **Visualization** — matplotlib, seaborn
- **Environment** — Jupyter Notebook

## Next Steps

- Segment by Job_Level *within* high-automation roles to see if seniority protects even in the riskiest job categories
- Build a predictive model (Random Forest / Logistic Regression) to rank all features by importance simultaneously
- Explore AI_Training_Hours as a time-series factor rather than a snapshot (this dataset is a single point in time, so causality can't be confirmed here)

## Files

- `Ai_Impact_On_Job_Analysis.ipynb` — full analysis notebook
- `ai-impact-jobs-layoff-risk-dataset.xlsx` — source dataset
- `requirements.txt` — Python dependencies

---
*Part of an ongoing data analyst portfolio. See more projects at [your portfolio link].*
