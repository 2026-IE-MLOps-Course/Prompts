# 🚀 MLOps Course: AI Prompt Library

*“Most Artificial Intelligence projects do not fail because of poor models... they fail because they never leave the notebook.”*

This repository contains the AI prompts used in the course **MLOps: From Notebook to Production** (Master in Business Analytics & Data Science).

These prompts are designed to generate scaffolding and boilerplate so you can focus on what actually matters:

- Understanding core MLOps concepts (Separation of Concerns, DRY, Reproducibility, Traceability)
- Making sound engineering trade-offs
- Connecting technical decisions to real-world business value

These prompts are not answers. They are accelerators.

---

# 🛠️ How to Use These Prompts

To get the most value from these tools, you must act as an architect, not a typist.

## Recommended Workflow

1. Open the `.txt` prompt for the current session.
2. Paste it into your AI assistant using Study or Guided Learning mode.
3. Generate the scaffolding.
4. Stop and read. Do not run anything yet.
5. Manually create the files in your local environment.
6. Paste the generated boilerplate into the appropriate files.
7. Locate all `TODO_STUDENT` blocks.
8. Replace the baseline logic with your own notebook logic.
9. Run the verification commands.
10. If something breaks, read the error trace and attempt to fix it before asking the AI for help.

---

# 🔄 The Zero-to-One Experience (Important)

The scaffolding is designed to run successfully out of the box.

When you execute:

    python -m src.main

The pipeline will:

- Attempt to load your raw dataset
- If the file does not exist:
  - Automatically create a small deterministic sample dataset at `data/raw/sample.csv`
  - Print a clear message explaining that this dataset is for scaffolding only
  - Train a simple baseline model
  - Produce the required artifacts

This guarantees a smooth first run and allows you to see the architecture working before integrating your real logic.

---

## ⚠️ Critical Rule

The generated sample dataset is NOT your assignment dataset.

Before doing real modeling work, you must:

1. Replace the sample CSV in `data/raw/` with your real dataset
2. Update `RAW_DATA_PATH` in `src/main.py`
3. Update `TARGET_COLUMN`
4. Replace baseline logic inside the `TODO_STUDENT` blocks

If you accidentally train on the sample dataset, your model is meaningless.

---

# 🛑 The Do Not Paste Until Checklist

Before committing any generated code, you must be able to answer:

- What does this code do, in plain English?
- What inputs does it expect, and what outputs does it produce?
- What assumptions does it make about the data or the environment?
- What could break in production, and how would the pipeline detect it?
- What business risk does this reduce? What business value does this enable?

If you cannot answer these questions, you are not ready to paste the code.

---

# 🧠 Why This Architecture Matters

This repository structure mirrors real-world MLOps systems.

It enforces:

- Separation of Concerns
- Reproducibility
- Traceability
- Fail Fast principles
- Baseline First, Then Improve

This is how production AI systems are built. Not in a notebook cell-by-cell.

---

# 🏆 The Quality Bar

Any code and documentation you commit using these tools must be:

- Reproducible
- Readable
- Traceable
- Deterministic
- Aligned with session goals

---

# 🔐 Academic Integrity

These prompts are learning accelerators.

Blind copy-paste will surface during debugging, deployment, and exams.

You are accountable for everything you commit and present.

AI is a productivity tool. It is not a substitute for understanding.

---

# 🎯 Final Reminder

The goal of this course is not to learn how to prompt AI.

The goal is to understand:

- How to move from notebook to production
- How to design reliable pipelines
- How to reduce model risk
- How to generate measurable business value from AI systems

The prompts help you build the scaffolding.

You are responsible for building the system.
