# Intro to Applied AI for Medics & Biomedical Scientists — Course Syllabus

> A short, practical course to familiarise medics and biomedical scientists (advanced undergrads & MSc students) with contemporary AI models, prompt engineering, and simple prototype building using no-code and low-code tools.

### Course Overview

This course introduces biomedical students to AI.

- Students will learn about AI, no code and low code tools. 
- They will learn how to load data and quickly visualize it and derive results. 
- Basics statistics
- They will also learn the basics of using large-language models (LLMs).
- They will also learn prompt engineering
- Responsible AI/AI ethics
- Rapid prototyping/HCI
- Hackathons (such as creating a clinical chatbot)


**Level:** Undergraduate/Postgraduate
**Prerequisites:** Basic programming knowledge (any language)  
**Duration:** 12 weeks (3 hours/week lecture + 2 hours/week lab)  

**Course Instructor:** Soumya Banerjee

**Course Website:** [https://neelsoumya.github.io/teaching_web_development/](https://neelsoumya.github.io/teaching_web_development/)


### Course Materials

Course content and materials can be found in the following files:

- [Content](materials/content.md)
- [Resources](materials/resources.md)
- [Setup instructions](materials/setup.md)
- [Command line](materials/command_line.md)
- [HCI principles and universal accessibility](materials/HCI.md)
- [Exams and quizzes](materials/exams_and_quizzes.md)
- [Student Projects](materials/projects.md)
<!--
### Instructor Information
 - [Extra information](materials/extra.md)
-->


---

## Course summary (target: MSc / advanced undergrads)

**Length:** 6–8 weeks (one 2-hour session/week + 2–3 hrs practical work) — or stretch to a 10-week term with extra labs.
**Prereqs:** basic statistics (mean/SD, sensitivity/specificity) helpful; **no programming required**.

**Overall learning goals**

1. Understand what contemporary AI models (language models, classifiers, simple vision models) *do* and their limitations.
2. Be able to interact productively with LLMs (prompt engineering) and no-code AI tools.
3. Build tiny prototypes: (a) a text prompt / summariser; (b) a simple classifier (using a public, de-identified dataset) and a browser demo (Gradio/Streamlit).
4. Learn basic evaluation and ethical checks (bias, data leakage, privacy).

---

## Weekly syllabus (compact 8-week version)

### Week 0 — Intro & motivation

* Why clinicians/scientists should know AI (high-level examples, limitations).
* Course logistics, ethics & data privacy primer.

### Week 1 — “What is an AI model?” (no code)

* Types: regression, classifiers, image models, LLMs.
* Hands-on: try OpenAI Playground (or equivalent) to see a model answer simple prompts. ([Learn Prompting][1])

### Week 2 — Prompt engineering & evaluation (practical, no code)

* Techniques: explicit instructions, chain-of-thought, few-shot, controlling tone and output length.
* Lab: students write prompts to summarise a clinical paragraph and evaluate accuracy.

### Week 3 — No-code model demos & sharing

* Introduce Hugging Face Spaces + Gradio for quick demos; show how a prebuilt model can be run in-browser.
* Short lab: run a text-classification demo on Hugging Face Spaces. ([Hugging Face][2])

### Week 4 — Lightweight Python: Colab + scikit-learn (first model)

* Demonstration: load a classic dataset (e.g., Breast Cancer WDBC), train a logistic regression, inspect confusion matrix.
* Use Google Colab so students don’t need local setup. ([Teaching with Colab][3])

### Week 5 — Small app: wrap model in a Gradio/Streamlit demo

* Show 5–10 lines to convert the model into a web demo (Gradio preferred for quick demos; Streamlit for polished dashboards).
* Compare trade-offs briefly. ([Gradio intro][5], [Gradio vs Streamlit][4])

### Week 6 — Evaluation, pitfalls, and reproducibility

* Cross-validation, class imbalance, calibration, data leakage, and safe release.
* Group discussion: where would you *not* trust an AI?

### Week 7 — Mini project sprint presentations

* In-class demos via Spaces / Colab / Gradio.

### Week 8 — Reflection, ethics deep-dive, next steps and resources

---

## Recommended toolchain (no-code → low-code)

* **OpenAI Playground / equivalent** — rapid prompt experiments and seeing LLM behaviour interactively. Great for learning prompting before coding. ([Learn Prompting][1])
* **Hugging Face Spaces + Gradio** — host interactive demos quickly in the browser; students can fork/clone templates and share. Great for non-dev students to try models. ([Hugging Face][2])
* **Gradio (Python)** — very few lines to wrap a model into a UI (ideal first demo). ([Gradio intro][5])
* **Streamlit** — alternative if you want more complex dashboards (choose Streamlit for polished UI; Gradio for faster prototyping). ([Gradio vs Streamlit][4])
* **Google Colab** — zero-install Python notebooks for teaching and sharing notebooks. Perfect for scikit-learn demos. ([Teaching with Colab][3])

---

## Datasets (use only publicly available / de-identified / synthetic data)

Suggested safe starters (small, well-documented, easy to load):

* **Breast Cancer Wisconsin (Diagnostic)** — classic small classification dataset, available inside scikit-learn. Great for first modelling lab. ([scikit-learn `load_breast_cancer`][6])
* **UCI Heart Disease (Cleveland subset)** — another small tabular dataset useful for teaching binary classification and metrics. (Emphasise limits and small sample sizes.) ([UCI Heart Disease][7])
* **PhysioNet** — many physiological research datasets; some require credentialed access — good for ECG/PPG/time-series later. Emphasise access rules / governance. ([PhysioNet][8])

**Rule:** avoid any dataset containing identifiable patient info unless the students/team have IRB/ethics approval and you follow local governance.

---

## Project ideas (easy → ambitious)

1. **Prompt & critique (easy, solo)**

   * **Task:** craft prompts to summarise a short clinical note in plain English + produce bullet-point management suggestions.
   * **Deliverable:** 3 different prompts, comparison table of accuracy, one paragraph reflection on hallucinations/limits.
   * **Tools:** OpenAI Playground or similar. ([Learn Prompting][1])

2. **Diagnostic checklist assistant (easy, group)**

   * **Task:** build a Gradio demo that takes a short patient vignette and returns likely differential diagnoses (from a simple ruleset / LLM).
   * **Focus:** prompt design and evaluation, not clinical decision-making.
   * **Deliverable:** live demo on Hugging Face Spaces + short accuracy note. ([Hugging Face][2])

3. **Basic classifier + demo (medium)**

   * **Task:** using scikit-learn and the breast cancer dataset, train a logistic regression and expose it via a Gradio app that lets users input numeric features and see predicted class + probability.
   * **Deliverable:** Colab notebook + Gradio demo link; short report covering performance (accuracy, sensitivity, specificity). ([scikit-learn `load_breast_cancer`][6])

4. **Text mining for literature (medium)**

   * **Task:** given a small corpus of abstracts (public domain), build an LLM prompt pipeline to extract PICO elements (Population, Intervention, Comparison, Outcome). Evaluate precision/recall via manual labels.
   * **Deliverable:** Colab notebook + evaluation table.

5. **Signal classification (ambitious)**

   * **Task:** use an open PhysioNet dataset (e.g., arrhythmia subset if accessible) to make a simple time-series classifier (feature extraction → RF/LogReg). Emphasise preprocessing + reproducibility. ([PhysioNet][8])

6. **Clinical language assistant (advanced, ethics focus)**

   * **Task:** build a prompt-based assistant that turns clinical notes into patient-facing explanations. Evaluate for accuracy, privacy leakage, and readability. Deliver a risk-log and mitigation plan.

7. **Reproducible demo + README (all levels)**

   * **Requirement:** every project must include a README with: how to run, what data was used (and license), evaluation, and ethical considerations. Deploy to a Space or provide a Colab link.

---

## Tiny Colab-ready Python starter (copy/paste into Colab)

> Safe, short demo using scikit-learn’s breast cancer dataset (no PHI). Students can run and see training + accuracy in a few seconds.

```python
# Run in Google Colab
from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load data
data = load_breast_cancer()
X, y = data.data, data.target
feature_names = data.feature_names

# Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.25, random_state=42, stratify=y
)

# Train
model = LogisticRegression(max_iter=1000)
model.fit(X_train, y_train)

# Evaluate
y_pred = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Confusion matrix:\n", confusion_matrix(y_test, y_pred))
print("\nFull report:\n", classification_report(y_test, y_pred, target_names=data.target_names))
```

**Tip:** wrap `model.predict_proba` into a tiny Gradio app in ~5–10 lines to make a browser UI (see Gradio docs). ([Gradio intro][5])

---

## Assessment & grading suggestions

* **50%** project (working demo + reproducible notebook / README)
* **30%** short report (methods, evaluation, ethical/social reflection)
* **20%** small weekly tasks (prompts, short quizzes on concepts)

---

## Ethics, safety & teaching notes (very important)

* Emphasise models’ **limitations**: hallucinations, calibration issues, and the danger of trusting probabilistic outputs as hard facts.
* Use only public / fully deidentified datasets unless you have explicit governance approval. For sensitive data, require documented approvals and data handling plans. Cite PhysioNet access rules when appropriate. ([PhysioNet][8])
* Teach students to evaluate models on clinically meaningful metrics (sensitivity/specificity, PPV/NPV, calibration curves, decision curves) — not just accuracy.

---

## Helpful links / docs for students & instructors

* [Learn Prompting — OpenAI Playground guide][1]
* [Hugging Face Spaces — overview][2]
* [Teaching with Google Colab (Part 1) — Medium][3]
* [Gradio vs Streamlit: Choosing a Tool][4]
* [Introduction to Gradio — Hugging Face LLM Course][5]
* [scikit-learn `load_breast_cancer` reference][6]
* [UCI Heart Disease (Cleveland) — UCI Repository][7]
* [PhysioNet][8]

---


### References

[1]: https://learnprompting.org/docs/intermediate/openai_playground?srsltid=AfmBOorErrn0h-8CgtMsnJAG_JNhQV8ylQt4IOkW4c7SaahbiBp92U_g&utm_source=chatgpt.com "How to Set Up and Use the OpenAI Playground?"
[2]: https://huggingface.co/docs/hub/en/spaces-overview?utm_source=chatgpt.com "Spaces Overview - Hugging Face"
[3]: https://medium.com/google-colab/teaching-with-colab-part-1-96b81419a368?utm_source=chatgpt.com "Teaching with Colab (Part 1) - Medium"
[4]: https://evidence.dev/learn/gradio-vs-streamlit?utm_source=chatgpt.com "Gradio vs. Streamlit: Choosing a Tool for Your Data App"
[5]: https://huggingface.co/learn/llm-course/en/chapter9/1?utm_source=chatgpt.com "Introduction to Gradio - Hugging Face LLM Course"
[6]: https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html?utm_source=chatgpt.com "load_breast_cancer"
[7]: https://archive.ics.uci.edu/dataset/45/heart%2Bdisease?utm_source=chatgpt.com "Heart Disease - UCI Machine Learning Repository"
[8]: https://physionet.org/?utm_source=chatgpt.com "PhysioNet"
