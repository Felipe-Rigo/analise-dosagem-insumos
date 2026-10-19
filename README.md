# Ingredient Dosing Analysis (Batch Process)

Python notebook for statistical analysis of automatic ingredient dosing (flour, fat, water) and temperature in a batch mixing process. It compares what the system was set to dose (**setpoint**) with what was actually dosed (**actual**), batch by batch.

> **All data in this repository is synthetic.** It was randomly generated for demonstration and does not represent any real recipe, equipment or company result.

## What the notebook does

1. **Load and prepare** batch data from Excel (`pandas`)
2. **Explore** distributions (histogram + KDE), outliers (boxplots) and the series per batch
3. **Control chart** with the mean and ±% limits around it
4. **Process capability** (histogram vs. specification limits)
5. **Cp / Cpk** per ingredient
6. **Deviation vs. setpoint (%)** and **ramp-up** analysis of the first 30 batches

## Data format

`data/bateladas_exemplo.xlsx`, sheet `BD`, one row per batch:

| Column | Meaning |
|---|---|
| `Bateladas` | Batch number |
| `Farinha_s` / `Farinha_r` | Flour: setpoint / actual |
| `Gordura_s` / `Gordura_r` | Fat: setpoint / actual |
| `Agua_s` / `Agua_r` | Water: setpoint / actual |
| `Temp_s` / `Temp_r` | Temperature: setpoint / actual |

## How to run

```bash
pip install pandas numpy matplotlib seaborn scipy openpyxl jupyter
jupyter notebook analise_dosagens.ipynb
```

Run it from the repository folder so the relative path `data/bateladas_exemplo.xlsx` resolves.

## Tech stack

Python · Pandas · NumPy · Matplotlib · Seaborn · SciPy
