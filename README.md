[README.md](https://github.com/user-attachments/files/32397508/README.md)
# Data Quality Profiling — Big Mac Index

## Objective

Evaluate the Big Mac Index as a purchasing-power-parity dataset by correcting valuation logic, diagnosing incomplete panel data, and measuring the effects of data-selection decisions.

## Methodology

- Corrected a PPP valuation calculation that reversed the subtraction order and produced backward results.
- Ranked currencies by their July 2024 valuation relative to the US dollar.
- Identified survivorship bias caused by restricting the analysis to units observed in every period.
- Compared the complete-panel average with the average using all available observations.
- Developed `profile_dataframe()` to report dataset shape, units, periods, structure, complete units, panel balance, and column-level missingness.
- Distinguished absent country-period rows from null values within existing rows.

## Key Findings

- Switzerland was the most overvalued currency in July 2024 at **41.76%**, followed by Uruguay at **24.29%**.
- The complete-panel method overstated the average Big Mac price by **$0.081, or 2.1%, on average**.
- The complete-panel average was higher than the all-available average in **33 of 45 periods**.
- The dataset contains **2,056 rows and 19 columns**, covering **57 units across 45 periods**.
- Only **25 units** appear in every period, so the panel is **unbalanced**.
- **Seven columns** have more than 10% missing values.

## Conclusion

The analysis shows that technically correct calculations can still produce misleading conclusions when data coverage and panel completeness are ignored. Using all available observations and clearly reporting missingness provides a more transparent view of global Big Mac price trends.
