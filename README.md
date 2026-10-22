# MLOps Course: AI Prompt Library

*"Most Artificial Intelligence projects do not fail because of poor models... they fail because they never leave the notebook."*

Prompts for the course **MLOps: From Notebook to Production** (Master in Business Analytics and Data Science). They generate plumbing so your team can spend its time on engineering trade-offs and business value.

These prompts are not answers. They are accelerators.

---

## Prompts

| Prompt | Sessions | What you get |
|---|---|---|
| [`MLOps_Kickoff_Scaffold.md`](MLOps_Kickoff_Scaffold.md) | 2 to 5 | Draft versions of every kick-off skeleton file: working plumbing, temporary placeholders and marked spaces, with guiding questions, for your own code |

---

## How to use the kick-off prompt

You act as the architect. The AI drafts the plumbing.

1. Open any AI chatbot or coding agent and paste the prompt
2. Answer its questions: team and file owners, use case, data columns, target, problem type
3. It returns drafts in 3 batches (chatbots) or in a `_scaffold/` folder (agents). **It never touches your files**
4. Each owner copies their file(s) into the repo on their own branch, one file at a time
5. Run `python -m src.main` after each file. The pipeline must keep running
6. Open each `STUDENT CODE` block, answer its questions, then write (or vibe-code) your own logic

## Markers in the drafts

| Marker | Meaning | Your action |
|---|---|---|
| `[PLUMBING]` | Generic code that works as is | Read and understand it |
| `[CONTRACT]` | Other files depend on this name, parameter or return type | Change only with the `main.py` owner, update all callers in the same PR |
| `[ASSUMPTION]` | Something assumed about your data | Check it holds |
| `[TEMP]` | Placeholder so the pipeline runs (dummy model, simple metric, demo data) | Replace it |
| `STUDENT CODE START/END` | Your team's decisions and code | Answer the questions, then code |

---

## The first run

```bash
python notebooks/temp_make_demo_data.py   # only if you need demo files
python -m src.main
python -m pytest                          # use "python -m": plain "pytest" needs pytest.ini (stage 2)
```

The placeholder pipeline loads, cleans, validates, splits into train, validation and test **before** anything is fitted, trains a dummy baseline and writes:

- `data/processed/clean.csv`
- `models/model.joblib`
- `reports/predictions.csv`

The dummy model is the score to beat, not a result.

---

## Before you commit, answer these

- What does this code do, in plain English?
- What are its inputs and outputs?
- What risk does it reduce (for example data leakage or training-serving skew)?
- What business value does it enable?

---

## Academic integrity

You are accountable for every line you commit. Code you cannot explain will surface in reviews, debugging and the exam. AI is a productivity tool, not a substitute for understanding.

The goal is not to learn how to prompt. It is to learn how to build reliable, production-ready AI pipelines.
