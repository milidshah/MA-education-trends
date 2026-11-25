# MA-education-trends

## Instructions to reproduce results

### 1. Replication Package Contents

---
replication_package/
├── README.md                  # this file
├── ma-educ-analysis.qmd       # all code: cleaning, EDA, Models 1-3
├── ma-educ-analysis.pdf       # rendered output (all results)
├── MA-education-trends.Rproj  # RStudio users can use it to swd to project folder     
├── sessionInfo.txt            # R and package versions used
└── data/
    ├── teacher_retention.csv
    ├── student_achievement.csv
    └── hs_grad_rates.csv
---

### 2. Software Requirements

- R version 4.5.2 (2025-10-31)

- Quarto version 1.5.54 to render the `qmd` file

- LaTeX installation for PDF output (not necessary, but I have used it for `ma-educ-analysis.pdf`): `quarto install tinytex`

| package         | version |
|:----------------|:--------|
| tidyverse       | 2.0.0   |
| patchwork       | 1.3.2   |
| knitr           | 1.51    |
| skimr           | 2.2.2   |
| fixest          | 0.14.2  |
| marginaleffects | 1.0.0   |

Install necessary packages with:

```{r}
install.packages(c("tidyverse", "fixest", "marginaleffects", "patchwork", "knitr", "skimr"))
```

### 3. Data

All data are public and come from the Massachusetts Department of Elementary and Secondary Education (DESE) Education-to-Career Research and Data Hub. The original files used in the analysis are included in `data/`, unmodified. They were downloaded on 11-21-2026.

| File in `/data` | Dataset | Source (export as CSV) | Documentation |
|----|----|----|----|
| teacher_retention.csv | Elementary and Secondary Staff Retention Rates | <https://educationtocareer.data.mass.gov/api/v3/views/52c5-e56a/export.csv> | <https://educationtocareer.data.mass.gov/d/52c5-e56a> |
| student_achievement.csv | MCAS Achievement Results | <https://educationtocareer.data.mass.gov/api/v3/views/i9w6-niyt/export.csv> | <https://educationtocareer.data.mass.gov/d/i9w6-niyt> |
| hs_grad_rates.csv | High School Graduation Rates | <https://educationtocareer.data.mass.gov/api/v3/views/n2xa-p822/export.csv> | <https://educationtocareer.data.mass.gov/d/n2xa-p822> |

### 4. Reproduce the results

1.  Unzip the replication package and keep the folder structure as is.

2.  Open a terminal in the `replication_package/` folder and run:

    ```{bash}
    quarto render ma-educ-analysis.qmd
    ```

    - or open the `.qmd` file in RStudio and click Render
