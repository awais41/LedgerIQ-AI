# LedgerIQ AI

AI-assisted financial intelligence for transaction data.

LedgerIQ transforms raw business transactions into a structured analysis workflow covering cleaning, categorization, trend analysis, anomaly detection, budgeting, cash-flow forecasting, cost review, and AI-assisted summaries.

## Workflow

```text
CSV
→ validation and cleaning
→ categorization
→ analytics
→ duplicate review
→ anomaly and risk signals
→ budgets
→ recurring expenses
→ cash-flow forecast
→ cost optimization
→ AI-assisted summary
→ exportable reports
```

## Features

- CSV upload and validation
- Duplicate detection and cleanup
- Automatic transaction categorization
- Revenue, expense, and net cash-flow KPIs
- Monthly trend and category analysis
- Client profitability analysis when a `client` column is available
- Recurring-expense detection
- Isolation Forest anomaly detection
- Review-oriented risk scoring
- Budget monitoring
- 7–90 day baseline cash-flow forecasting
- Cost-optimization recommendations
- AI-assisted CFO-style summaries through an OpenRouter-compatible endpoint
- CSV and text report export

## Input Schema

Required columns:

```text
date, description, amount
```

Optional columns:

```text
category, client, type
```

Positive `amount` values represent income. Negative values represent expenses.

## Run Locally

```bash
python -m venv .venv
```

Activate the environment:

```bash
# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate
```

Install dependencies and start the app:

```bash
pip install -r requirements.txt
streamlit run app.py
```

Use **Load demo data** to explore the product immediately, or upload a compatible CSV file.

## AI Configuration

Copy `.env.example` to `.env` and set `OPENROUTER_API_KEY` if you want to enable the external AI summary layer.

The application can still run without an API key by using its local fallback behavior.

## Engineering Notes

LedgerIQ is designed as a decision-support application, not as an accounting system. Its anomaly and risk indicators surface records for review; they do not prove fraud, and the application does not provide financial advice.

## Tech Stack

`Python` · `Pandas` · `scikit-learn` · `Streamlit` · `Isolation Forest` · `OpenRouter-compatible LLM API`
