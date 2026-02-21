# 🚀 MLOps Course: AI Prompt Library

*“Most Artificial Intelligence projects do not fail because of poor models... they fail because they never leave the notebook!”*

This repository contains the AI prompts used in the course **MLOps: From Notebook to Production** (Master in Business Analytics & Data Science). 

These prompts are designed to generate **scaffolding and boilerplate** so you can spend your time on what actually matters:
* Understanding core MLOps concepts (Separation of Concerns, DRY, Reproducibility).
* Making sound engineering trade-offs.
* Connecting technical decisions to real-world business value.

These prompts are not answers. They are **accelerators**.

---

## 🛠️ How to Use These Prompts

To get the most out of these tools, you must act as an architect, not a typist. 

**The Recommended Workflow:**
1. Open the `.txt` prompt for the current session.
2. Paste it into your AI assistant, specifically instructing it to use **"Study"** or **"Guided Learning"** mode.
3. Generate the scaffolding.
4. **Stop and Read.** Do not run anything yet. 
5. Manually create the files in your local environment and paste the generated boilerplate.
6. Hunt down the `TODO_STUDENT` blocks and implement your own Data Science logic.
7. Run the verification commands. If it breaks, attempt to fix it yourself by reading the error trace before asking the AI for the answer.

---

## 🛑 The "Do Not Paste Until..." Checklist (Non-Negotiable)

You are expected to use AI to support your learning, not replace it. If you blindly copy AI output, your pipeline *will* break during the final deployment, and you will not know how to fix it.

Before you commit any generated code into your repository, you must be able to answer these five questions:

* **The English Translation:** What does this code do, in plain English?
* **The Contract:** What inputs does it expect, and what outputs does it produce?
* **The Assumptions:** What assumptions does it make about the data or the system environment?
* **The Quality Gate:** What could break in production, and how would this pipeline detect it?
* **The "So What?":** What business risk does this code reduce, or what business value does it enable?

**If you cannot answer these, you are not ready to paste it.**

---

## 🏆 The Quality Bar 

Any code and documentation you commit using these tools must be:
* **Reproducible:** Runs flawlessly on a clean machine (using your `environment.yml`).
* **Readable:** Easily understood by a peer who hasn't seen the code before.
* **Traceable:** Uses clear artifacts, filenames, and sequential pipeline steps.
* **Aligned:** Matches the specific session goals without introducing overly clever, unnecessary complexity.