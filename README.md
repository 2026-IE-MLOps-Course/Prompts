# 🚀 MLOps Course: AI Prompt Library

*“Most Artificial Intelligence projects do not fail because of poor models... they fail because they never leave the notebook.”*

This repository contains the AI prompts used in the course **MLOps: From Notebook to Production** (Master in Business Analytics & Data Science). These prompts are designed to generate scaffolding and boilerplate so you can focus on making sound engineering trade-offs and connecting technical decisions to real-world business value

These prompts are not answers. They are accelerators

---

# 🛠️ How to Use These Prompts

To get the most value from these tools, you must act as an architect, not a typist

## Recommended Workflow

1. Open the `.txt` prompt for the current session
2. Paste it into your AI assistant using Study or Guided Learning mode
3. Generate the scaffolding
4. Stop and read, do not run anything yet
5. Manually create the files in your local environment
6. Paste the generated boilerplate into the appropriate files
7. Locate all `TODO_STUDENT` blocks
8. Replace the baseline logic with your own notebook logic
9. Run the verification commands
10. Debug by reading the error trace before asking the AI for help

---

# 🔄 The Zero-to-One Experience

The scaffolding is designed to run successfully out of the box. When you execute:

```bash
python -m src.main
```

The pipeline will:

- Attempt to load your raw dataset
- Auto-generate scaffolding data if the dataset is missing by creating a small deterministic sample at `data/raw/sample.csv`
- Run a leakage-safe flow using a `scikit-learn Pipeline` and `ColumnTransformer`
- Produce artifacts including clean data, a model, and a predictions report

This guarantees a smooth first run so you can see the architecture working before integrating your real logic

---

# 🧱 What You Are Building

## Current Pipeline Boundary

We are currently locking in the core engine of the system:

**Load → Clean → Split → Build Feature Recipe → Train → Save Artifact**

### Key Rule for Leakage Prevention

- Split first: split into train and test before any stateful learning step
- Pipeline fitting: fit the full `Pipeline` (preprocessing + model) on training data only
- Any transformation that learns from the data distribution (quantiles, encoders, scalers) must never see the test data

## Repo Structure (Core Modules)

You will incrementally build these modules under `src/`

- `load_data.py` ingestion only, creates sample data if needed
- `clean_data.py` stateless cleaning, no I/O or modeling
- `features.py` defines the `ColumnTransformer` recipe, no `.fit()` calls
- `train.py` bundles preprocessing and model into a single `Pipeline`
- `main.py` orchestrates the flow and owns the train/test split
- `utils.py` boilerplate I/O plumbing (loading and saving)

---

# 🔧 Configuration and the YAML Bridge

Until `config.yml` is introduced, the project uses a nested **`SETTINGS` dictionary** in `src/main.py`. This mirrors the structure of a YAML file to make future refactoring seamless

## Critical Configuration Steps

The sample dataset is for scaffolding only. To do real work, you must:

1. Replace the sample CSV in `data/raw/` with your real data
2. Set `"is_example_config": False` in the `SETTINGS` dictionary
3. Map feature groups by updating the `quantile_bin`, `categorical_onehot`, and `numeric_passthrough` lists in `SETTINGS` to match your column names

---

# 📦 Required Artifacts

A successful run must produce:

- `data/processed/clean.csv`
- `models/model.joblib`
- `reports/predictions.csv`

---

# 🛑 The Do Not Paste Until Checklist

Before committing code, ensure you can answer:

- What does this code do in plain English?
- What are the inputs and outputs?
- What risk does this reduce (for example data leakage, training-serving skew)
- What business value does this enable?

---

# 🔐 Academic Integrity

These prompts are learning accelerators. Blind copy-paste will surface during debugging and exams. You are accountable for everything you commit. AI is a productivity tool, not a substitute for understanding

The goal is not to learn how to prompt. It is to learn how to design reliable, production-ready AI pipelines
