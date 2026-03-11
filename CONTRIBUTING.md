# Contributing Guidelines

Thank you for contributing to ISE302 – Data Mining Group Project. Please read the rules below carefully before making any commits or opening pull requests.

---

## Branching Rules

- **Do NOT push to `main`** unless the commit is shared preprocessing or EDA work (Phase 1). All Phase 2 individual model work must stay on student branches.
- **Each student pushes ONLY to their own `student/<firstname-lastname>` branch.** Never push to another student's branch.
- **Do not open pull requests from student branches until Week 11.** PRs to `main` / `results` will only be accepted after the competition phase ends.

## Commit Message Format

All commit messages must follow this format:

```
[phase] short description
```

**Examples:**

```
[preprocessing] add outlier detection for age column
[eda] plot correlation heatmap
[model] train random forest baseline
[model] tune hyperparameters with GridSearchCV
[results] add confusion matrix plot
[docs] update team member table in README
```

**Valid phase tags:** `preprocessing`, `eda`, `model`, `results`, `docs`, `fix`

## Setting Up Your Student Folder

1. Copy `students/_TEMPLATE/` to `students/<your-firstname-lastname>/`.
2. Checkout your personal branch: `git checkout -b student/<your-firstname-lastname>`.
3. Work only inside `students/<your-firstname-lastname>/`.
4. Do not modify files in `data/`, `shared/`, or another student's folder.

## Pull Request Checklist (Week 11+)

- [ ] All cells in `model.ipynb` have been run and output is visible.
- [ ] `results/` folder contains at least one saved plot and a metrics summary.
- [ ] `README.md` inside your student folder is fully filled in (name, algorithm, metric table).
- [ ] No large binary files (> 50 MB) are committed.
- [ ] All commit messages follow the `[phase] description` format.
