# Variance Decoded
## Supply Chain Cost Variance Analysis for Aerospace & Defense

### The Problem
Your company ordered $500M of materials. Actual spend: $525M. Variance: $25M unfavorable.

Finance presents to the board: "We overspent by 5%."

But supply chain knows the real story:
- Titanium prices surged 30% (market, not your fault)
- Quality escape required $5M rework (but prevented $50M delivery delay)
- Expedited 200 shipments for $8M (prevented production stoppage)
- Negotiated new contracts and saved $12M

**Finance sees overspend. Supply chain managed a crisis. Nobody knows how to tell that story.**

### The Solution
This tool segments aerospace cost variance automatically into:
- **Price variance** (commodity market moves)
- **Volume variance** (ordered more/less)
- **Mix variance** (shifted to premium suppliers)
- **Quality variance** (rework, alternate sourcing)
- **Expedite variance** (fast shipping)
- **Efficiency variance** (process improvements)

Then it tells the real story: "Here's what's bad. Here's what's good risk management. Here's what was unavoidable."

### Key Features
- Automatic variance decomposition (price, volume, mix, efficiency, quality)
- Root cause linking (which supplier? which commodity?)
- Waterfall chart visualization
- Auto-generated board presentations
- Material variance flagging (identify the 20% that drives 80%)

### Steps taken:

1. **Install dependencies**:
```bash
   pip install -r requirements.txt
```

2. **Prepare data** (purchase orders + actual spend):
```python
   import pandas as pd
   from src.variance_engine import VarianceAnalyzer
   
   # Load data
   df = pd.read_csv('data/aerospace_variance.csv')
   
   # Analyze variance
   analyzer = VarianceAnalyzer(df)
   variance_breakdown = analyzer.decompose()
   
   # Generate report
   report = analyzer.generate_report()
   print(report)
```

3. **Run Streamlit dashboard**:
```bash
   streamlit run app/streamlit_dashboard.py
```

4. **Export to PowerPoint**:
```python
   from src.report_generator import generate_board_deck
   
   generate_board_deck(variance_breakdown, 'output.pptx')
```

### Dataset
- $500M annual procurement across 50 suppliers
- 10,000+ line items
- Tracked by commodity (Titanium, Composites, Electronics, etc.)
- Includes: budget, actual, supplier quality rating, on-time delivery %

### Core Insight
**"In aerospace, cost variance isn't bad—it's a safety/quality/schedule story."**

That "$25M overspend" is actually $18M market-driven (titanium surge), $8M risk management (quality rework that prevented $50M delay), and only $5M true inefficiency.

### Results
- Variance explanation: 10 hours → 1 hour
- Finance credibility: Improved (understands the real story)
- Supply chain credibility: Improved (gets credit for risk management)
- Board confidence: Increased (understands strategy, not just numbers)

### Technology Stack
- **SQL**: Query purchase orders, supplier data
- **Python**: Pandas, NumPy for decomposition
- **Visualization**: Plotly waterfall charts
- **Reporting**: Jinja2 + Python-pptx for auto-generation

### Files in This Repo
- `README.md` — This file
- `METHODOLOGY.md` — Variance decomposition formulas
- `notebooks/` — Jupyter notebooks
- `src/` — Python modules (variance engine, root cause, reporting)
- `app/` — Streamlit dashboard
- `data/` — Sample aerospace procurement data

### Next Steps
1. Load procurement and actual spend data
2. Run variance decomposition
3. Identify material variances (>5% of total)
4. Trace to root causes
5. Build the board presentation

### License
MIT

### Author
Veronica Marenco | Paris, France | [LinkedIn](https://linkedin.com/in/veronicamarenco)
