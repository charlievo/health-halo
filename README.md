# Health Halo — Do "Healthy" Labels Mean Healthier Food?

An analysis of 3,956 Australian food products to test whether "healthy" marketing claims actually predict nutritional quality.

**[View the interactive web dashboard →](https://charlievo.github.io/health-halo/)**
**[View the project write-up →](https://charlievo.github.io/health-halo/index.html)**

---

## The Question

Food products marketed as "healthy", "light", "natural" or "nutritious" are everywhere. But does the label actually mean the food is better for you? This project uses real product data and a predictive model to find out.

---

## Dashboards

| Dashboard | Description |
|-----------|-------------|
| [Interactive web dashboard](https://charlievo.github.io/health-halo/) | Built in HTML/CSS/JavaScript — explore health grades, marketing claims and nutritional drivers |
| [Project write-up](https://charlievo.github.io/health-halo/index.html) | Full methodology, decisions and findings |
| Power BI dashboard | See `powerbi-dashboard.png` in this repo for a static preview |

---

## The Data

- **Source:** [Open Food Facts](https://world.openfoodfacts.org/) — open-source, community-contributed food product database
- **Coverage:** 3,956 Australian food products with complete nutritional data
- **Health grades:** Nutri-Score (A–E), an established European nutritional rating system based on nutrient composition

---

## Method

1. **SQL (DuckDB)** — extracted and filtered Australian products from the raw Open Food Facts dataset
2. **Python (pandas, scikit-learn, SHAP)** — data cleaning, feature engineering and model building
3. **Model** — HistGradientBoostingClassifier predicting Nutri-Score grade from nutritional facts
   - Deliberately excluded marketing claims from model inputs to avoid circular results
   - Reported cross-validated accuracy (77%) rather than one-off test score
   - Used SHAP values to identify which nutritional features drive the grade
4. **Visualisation** — custom interactive web dashboard (HTML/JS) and Power BI

---

## Key Findings

- **1 in 3** foods marketed as "healthy" scored poorly (grade D or E) — about the same rate as food overall
- **Salt, sugar and saturated fat** drive the Nutri-Score grade far more than any label claim
- A "healthy" label is a weak signal at best — and no guarantee of nutritional quality

---

## Repo Contents

| File | Description |
|------|-------------|
| `health-halo-analysis.ipynb` | Full analysis notebook (SQL → cleaning → modelling → findings) |
| `dashboard.html` | Interactive web dashboard |
| `index.html` | Project write-up page |
| `powerbi-dashboard.png` | Power BI dashboard preview |

---

*by charlievo — self-directed project, 2026*
