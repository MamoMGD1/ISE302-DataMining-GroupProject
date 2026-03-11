# ISE302 – Data Mining Group Project

**Course:** ISE302 - Data Mining | **University:** Sakarya University
**Description:** A collaborative + competitive machine-learning project where the group jointly prepares data and each student independently builds their best predictive model.

---

## Project Overview

This project follows a two-phase workflow: in Phase 1 (Weeks 1–5) the entire group collaborated to collect, clean, explore, and preprocess the raw dataset, producing a single shared processed file that every student uses. In Phase 2 (Weeks 6–10) each student independently designed, trained, and evaluated their own machine-learning model on the processed data, competing for the best performance. All shared preprocessing work lives in the `shared/` and `data/` folders and represents joint contributions, while individual model work lives under `students/<name>/` on a personal branch. The final leaderboard comparing every student's results will be published in Week 11–12.

---

## Repository Structure

```
ISE302-DataMining-GroupProject/
│
├── data/
│   ├── raw_dataset.csv            # Original, unmodified collected dataset
│   └── processed_dataset.csv      # Cleaned, encoded, and scaled dataset (output of Phase 1)
│
├── shared/             # Collaborative notebooks: EDA, cleaning, encoding, scaling
│
├── students/
│   └── _TEMPLATE/      # Starter template every student copies to students/<their-name>/
│       ├── model.ipynb # Notebook scaffold with section headers to fill in
│       ├── results/    # Saved model artefacts, plots, and metric outputs
│       └── README.md   # Student-specific summary (name, algorithm, metrics)
│
├── docs/
│   └── final-report.pdf  # Final project report (added in Week 12)
│
├── .gitignore          # Python project ignores
├── requirements.txt    # Shared Python dependencies
├── CONTRIBUTING.md     # Branching rules and commit message conventions
└── README.md           # This file
```

---

## Phase 1 – Shared Work (Weeks 1–5)

All group members contributed equally to the following tasks. Commits touching the `shared/` and `data/` folders represent joint work.

- **Data Collection** – Identified and gathered the raw dataset; saved to `data/raw_dataset.csv`.
- **Exploratory Data Analysis (EDA)** – Examined distributions, correlations, and missing-value patterns.
- **Preprocessing**
  - Handling missing values (imputation / removal)
  - Outlier detection and treatment
  - Categorical encoding (label / one-hot encoding as appropriate)
  - Feature scaling (standardisation / min-max normalisation)
  - Preprocessed data saved to `data/processed_dataset.csv`

> **⚠️ Documentation requirement for all Phase 1 notebooks:**
> The code provided in each `shared/` notebook is a **placeholder template**, not a final solution. Every team is free to devise their own approach. What is mandatory is that **every code cell must be accompanied by a markdown cell** explaining (1) *what* was done and (2) *why* that specific approach was chosen — including the reasoning behind each decision. See `shared/README.md` for full details and examples.

---

## Phase 2 – Individual Models (Weeks 6–10)

Each student worked independently on their own branch (`student/<firstname-lastname>`). They loaded the shared processed dataset and built their own ML pipeline without collaboration on model code.

| Student Name | Algorithm | Branch | Accuracy | Notes |
|---|---|---|---|---|
| TBD | TBD | student/tbd | TBD | TBD |
| TBD | TBD | student/tbd | TBD | TBD |
| TBD | TBD | student/tbd | TBD | TBD |

---

## Final Results Leaderboard (Week 11–12)

> Results will be published here after the competition phase ends. Rankings are based on accuracy, visualization quality, model explainability, and real-world applicability.

---

## How to Use This Repo

1. **Clone the repository**
   ```bash
   git clone https://github.com/MamoMGD1/ISE302-DataMining-GroupProject.git
   cd ISE302-DataMining-GroupProject
   ```

2. **Install dependencies** *(Python ≥ 3.9 required)*
   ```bash
   pip install -r requirements.txt
   ```

3. **Access the clean dataset**
   Navigate to `data/processed_dataset.csv` – this is the preprocessed file produced in Phase 1 that all models are trained on.

4. **Explore a student's work**
   Navigate to `students/<student-name>/` and open `model.ipynb` to see that student's full ML pipeline and results.

---

## Branching Strategy

| Branch | Purpose |
|---|---|
| `main` | Shared work only – preprocessing, EDA, and project-wide documentation |
| `student/<firstname-lastname>` | Each student's personal branch for their individual model (Phase 2) |
| `results` | Final merged leaderboard branch, opened in Week 11 after all models are complete |

---

*ISE302 - Data Mining | Semester: 6 | Instructor: Dr. Esin Ayşe Zaimoğlu*
