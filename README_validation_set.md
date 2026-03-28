# Jura Heavy Metals — Validation Set EDA Dashboard

## Overview

This dashboard (`index.html`) delivers a fully interactive **Exploratory Data Analysis** of the strictly held-out 100-sample Swiss Jura geochemical validation dataset. Built as a zero-dependency, self-contained HTML file powered by **Chart.js**, it allows rigorous statistical comparison against the 259-sample prediction set before evaluating model performance.

## Contents of This Folder

| File | Purpose |
|---|---|
| `index.html` | Interactive EDA dashboard (open in any browser) |
| `gen_val_dashboard.py` | Python generator script — re-run to rebuild `index.html` |
| `jura_validation_set.csv` | Source data (100 samples, 12 columns) |

## Dashboard Sections

### 1. Summary Statistics (KPI Cards)
Seven colour-coded cards display the **mean, min, max, and standard deviation** for each heavy metal (Cd, Cu, Pb, Co, Cr, Ni, Zn) across the validation population.

### 2. Descriptive Statistics Table
Full statistical table per metal: Min · Q1 · Median · Mean · Q3 · Max · Std Dev — directly comparable to the prediction set statistics.

### 3. Frequency Distributions
Individual histogram panels per metal. Deviations from the training set histograms indicate potential distributional shift that could affect model generalisation.

### 4. Correlation Analysis
- **Pearson Correlation Heatmap** (bubble chart): verifies that metal co-occurrence relationships are preserved in the validation split relative to training.
- **Metal Pair Scatter Plot**: interactive drill-down for any two-metal pair.

### 5. By Rock Type & Land Use
- **Count by Rock Type** doughnut (ordered **youngest → oldest** per stratigraphic literature: Quaternary · Portlandian · Kimmeridgian · Sequanian · Argovian) — verifies geological representativeness of the holdout sample.
- **Count by Land Use** doughnut (Forest · Pasture · Meadow · Tillage)
- **Mean by Rock Type** and **Mean by Land Use** bar charts — selectable per metal

## Navigation
- **Spatial Maps →** Opens the live WGS84 geographic map dashboard for the validation set
- **← Prediction Set** Returns to the equivalent EDA dashboard for the 259-sample training set
