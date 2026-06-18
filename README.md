# Agriculture GDP and Education Disparities - Exploratory Data Analysis

> An original exploratory data analysis investigating the effect of agriculture GDP(%) on education disparities (financial, gender and region) across primary, lower secondary and upper secondary education levels in countries with major agricultural employment, from 2005 to 2023.

**Tech Stack:** Python · Pandas · Matplotlib · NumPy · Jupyter Notebook

**Data Sources:** World Bank - World Development Indicators · Education Statistics All Indicators (CC BY 4.0)

📄 **[View Full Report (PDF)](report.pdf)**

---

## Research Question

Does agricultural GDP(%) affect education completion disparities (financial, gender, urban/rural) in countries where a large percentage of the population works in agriculture?

No existing research was found linking these two concepts - making this an entirely original investigation.

---

## Key Findings

- A clear **inverse relationship** exists between agriculture GDP(%) and education completion disparities - as agricultural GDP increases, disparities decrease
- The effect is **negligible at primary level** (already high completion rates) but **most significant at upper secondary level**
- **Financial disparities** are the largest and most affected by agricultural GDP
- **Gender and regional disparities** follow a similar but less pronounced pattern

---

## Data Pipeline

1. **Agriculture dataset** - cleaned, outliers replaced using 3-standard-deviation rule, mean computed across 2005–2023, filtered to 78 countries with agricultural employment >35%
2. **Education dataset** - 60 series combinations (3 levels × 2 regions × 5 financial quintiles × 2 genders), cleaned, filtered to matching countries, mean computed across available years
3. **Disparity computation** - standard deviation across disparity categories used as the disparity metric
4. **Visualisation** - bar charts for completion rates across categories, scatter plots with lines of best fit for GDP vs disparity

---

## How to Run

Requires Python and Jupyter Notebook.

```bash
pip install pandas matplotlib numpy jupyter
jupyter notebook
```

Then open the `.ipynb` file. The datasets are included in the `archive/` folder so the notebook runs immediately without any additional setup.

---

## Data

Both datasets were downloaded from the World Bank under a CC BY 4.0 license and are included in the `archive/` folder:

- `archive/agriculture_data.csv` - World Development Indicators (employment and GDP indicators)
- `archive/education_data.csv` - Education Statistics All Indicators (completion rates)

---

## Limitations

- Mean values calculated across all years due to sparse yearly data - a time series analysis would yield richer insights
- Agriculture, forestry and fishing GDP(%) used as a proxy for agriculture GDP(%) - not an exact measure
- Single data source (World Bank) - cross-validation with another source would strengthen findings