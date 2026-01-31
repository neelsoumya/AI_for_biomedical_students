# Projects

Projects for students

## Project ideas

- Rapid prototyping/HCI
- Hackathons (such as creating a clinical chatbot)

### Explainable AI

- Explainable mortality prediction
- Privacy preserving synthetic data

## Miscellaneous projects

- LLM-based Clinical Data Imputation and LLM powered clinical aid
- Responsible AI/ AI safety for healthcare/ governance frameworks
- Patient and public involvement/HCI frameworks

## Higher level projects
- Healthcare foundation models that learn from longitudinal EHRs, clinical text, and multimodal data (such as genomic data). 
- Benchmarking and evaluation for healthcare AI
- Biomedical scientific agents

Application areas can be any field of medicine such as oncology, cardiovascular, infectious diseases, etc.


### Responsible AI

1. **Can AI internalize human morality?**
   **Objective:** Investigate whether AI systems can form and apply moral judgments that reflect human values.
   **Skills & methods:** Survey design, crowdsourced data collection, statistical analysis, and moral choice theory.

2. **Co-developing a taxonomy of AI risks**
   **Objective:** Build a grounded classification of AI-related risks by collaborating with a variety of stakeholders.
   **Skills & methods:** Co-design approaches, survey creation, statistical methods, and ethics of AI.

3. **Participatory auditing of AI systems**
   **Objective:** Create and assess community-driven auditing techniques for evaluating AI behaviour and harms.
   **Skills & methods:** Survey and experimental design, (web) development, and applied AI ethics.

4. **Visualization tools for responsible decision-making with AI**
   **Objective:** Design visual interfaces that help stakeholders make informed, responsible choices using AI outputs.
   **Skills & methods:** HCI, web development, and user-centred research.

5. **AI risks, opportunities, and media analysis at scale**
   **Objective:** Analyze how news media portray AI — its benefits and dangers — using large-scale text analysis.
   **Skills & methods:** Large-scale data analysis, natural language processing, and ethical reflection.

6. **AI governance from an organizational lens**
   **Objective:** Study how institutions govern AI by applying network and organisational analysis techniques.
   **Skills & methods:** Survey research, large-scale data analysis, and network science.



### Small language models (SLMs) for healthcare in Global South

For students are **medics first and programmers second**, the goal is to leverage their domain expertise for **data curation and evaluation** while using "low-code" tools for the actual training.

In the Global South, the primary barriers aren't just lack of doctors; they are **language barriers, medical jargon, and remote triage.** Small Language Models (SLMs) in the 1B–7B parameter range are perfect here because they can run on consumer laptops or cheap cloud instances.

Here are four concrete, small-scale project ideas:

---

## 1. The "Jargon Buster" for Rural Patients

**The Goal:** Fine-tune a model (like **Llama-3.2-3B** or **Phi-3.5-Mini**) to translate complex clinical diagnoses into local cultural metaphors or simplified language (e.g., Swahili, Hindi, or basic English).

* **Medical Task:** Taking a specialist’s note (e.g., *"Patient presents with idiopathic peripheral neuropathy"*) and explaining it as a rural health worker would to a patient (*"Your nerves are feeling weak for reasons we are still checking, like a wire with a loose connection"*).
* **Student Contribution:** Medics create a "Golden Dataset" of 200–500 pairs of "Doctor Speak" vs. "Patient Speak" tailored to a specific region.
* **Why it's "Small":** Requires very little data to see a massive improvement in tone and clarity.

## 2. Low-Resource Triage for Community Health Workers

**The Goal:** A decision-support SLM that helps non-doctor health workers in remote areas decide if a patient needs immediate transport to a city hospital.

* **Medical Task:** Input: Symptoms + Vital signs. Output: Triage category (Red/Yellow/Green) and a brief justification based on local resource constraints (e.g., *"Nearest oxygen is 4 hours away; refer now"*).
* **Dataset:** Use the **NLLB-Seed** (medical subset) or curate 500 examples of WHO Integrated Management of Childhood Illness (IMCI) guidelines.
* **Technical Fit:** Models like **BioMistral-7B** are already "medical-heavy" and just need a "nudge" via fine-tuning to follow specific triage logic.

## 3. Multilingual "Voice-to-Prescription" Assistant

**The Goal:** A model that takes a messy, spoken-style summary of a consultation in a local dialect and extracts a structured "Prescription & Plan" table.

* **Medical Task:** Converting a 2-minute dictated note into: *Medication | Dosage | Duration | Warnings.*
* **The "Global South" Twist:** Use **Bhashini** (for India) or **Masakhane** (for Africa) datasets to ensure the model understands local drug brand names and common local units of measurement.
* **Student Contribution:** Medics act as "Gold Standard" annotators, correcting the model’s drafts to build the fine-tuning set.

## 4. Chronic Disease "Check-in" Bot for SMS/WhatsApp

**The Goal:** A very "thin" model (1B parameters, like **Gemma-2B**) designed to handle follow-up questions for Diabetes or Hypertension via low-bandwidth text.

* **Medical Task:** Answering "What do I do if I missed my Metformin dose?" or "My feet are tingling, is that normal?" based on local clinical protocols.
* **Dataset:** Use the **NidaanKosh** (Indian diagnostic pattern) dataset or similar public health guidelines.
* **Technical Fit:** These models are small enough to be deployed on a single $10/month server, making them sustainable for local NGOs.

---

### The "Medic-Friendly" Technical Toolkit


1. **Model Selection:** Stick to **Llama-3.2 (1B/3B)** or **Phi-3.5-Mini**. They are incredibly smart for their tiny size.
2. **Fine-Tuning Tool:** Use **Unsloth** (via Google Colab). It’s a "wrapper" that makes fine-tuning 2x faster and uses 70% less memory. It’s essentially a 10-line Python script where they just point to their dataset.
3. **Data Generation:** Have the medics use a "Teacher Model" (like GPT-4o) to help them expand their 50 handwritten examples into 500 synthetic examples, which they then manually "audit" for medical accuracy.
4. **Evaluation:** This is where they shine. Instead of math metrics, have them perform a **"Blind Clinical Review"**—comparing the SLM's output against a human doctor and scoring it on a 1-5 scale for safety and empathy.

### Recommended Datasets (2026 Context)

* **India:** [AIKosh (IndiaAI)](https://aikosh.indiaai.gov.in/) — specifically the **NidaanKosh** lab records.
* **Africa:** [Lanfrica](https://lanfrica.com/) or **Zindi Africa** health challenges.
* **General:** **BioMistral** (an open-weight model already specialized for medicine).


### More ideas
Pactical, low-math, and runnable with Python + simple web UI or notebooks. Each idea shows a clear undergraduate scope and a natural master’s-level extension.

### Quick notes on common stacks

Python, Jupyter/Colab, Flask or Streamlit for a small UI, simple ML libs (scikit-learn, Hugging Face Transformers for prebuilt models), and basic REST calls to an LLM API (if allowed by your institution) are sufficient. Emphasize reproducibility: notebooks + README + short demo video.

---

### Project ideas (title → short plan, UG scope, MSc extension, tools & deliverables)

1. **Red-Team / Blue-Team Simulator for Prompt Safety**

* What: Build a small web app that lets one team supply “risky” prompts (simulated), and the other team builds simple rule-based / keyword or classifier defenses that block/transform them.
* UG: Implement rule filters + regex based sanitizer + UI to show blocked prompts.
* MSc: Add a lightweight classifier (fine-tune a small transformer or use scikit-learn on features) and evaluate precision/recall on a labeled dataset.
* Tools: Flask/Streamlit, scikit-learn, optionally Hugging Face inference.
* Deliverable: interactive demo, evaluation table, README.

2. **Output Provenance & Watermark Checker (Text)**

* What: Simulate a watermarking signal and create a detector that flags outputs likely produced by a model vs. human writing.
* UG: Implement simple statistical features (perplexity via a small LM, n-gram frequency) and a binary classifier.
* MSc: Implement and evaluate a known watermark detection scheme (simulation) and test robustness to paraphrase/noise.
* Tools: GPT API (optional), Hugging Face, scikit-learn.
* Deliverable: notebook with ROC curves, demo.

3. **Adaptive Content Moderation Pipeline**

* What: Build a modular pipeline that takes model output and applies a stack of checks (toxicity, misinformation, private data, policy) and returns an action (pass/flag/transform).
* UG: Implement two checks (toxicity via a pretrained classifier and profanity regex) and a simple policy engine (if X flagged → block).
* MSc: Add dynamic throttling (rate limits), contextual scoring, and evaluation on synthetic dataset.
* Tools: Streamlit UI, small pretrained classifiers.
* Deliverable: pipeline code + test suite + policy documentation.

4. **“Safe Suggestor” — Provide Non-Harmful Alternatives**

* What: Given a risky user request, generate (or select) safer alternative suggestions framed to satisfy user intent without harm.
* UG: Create rule-based templates that rewrite/deflect requests into safe alternatives and present options.
* MSc: Train a seq2seq model (or fine-tune a small model) for rewriting and evaluate semantic similarity vs. safety improvements.
* Tools: Transformers or API calls, BLEU/ROUGE or embedding similarity for evaluation.
* Deliverable: demo app + comparison table.

5. **Honeypot Interaction Logger to Study Malicious Prompts (Ethical, Simulated)**

* What: Create a sandboxed interface that logs anonymized interactions labeled by simulated intent categories (no real malicious content; use safe placeholders) to study patterns and triage.
* UG: Build the interface + logging + simple clustering to surface common patterns.
* MSc: Add active learning to prioritize which interactions to label or route to human review.
* Tools: Streamlit/Flask, scikit-learn clustering, SQLite.
* Deliverable: dataset (synthetic), analysis notebook.

6. **Model Output Robustness Checker (Paraphrase & Noise)**

* What: Test how small edits (typos, paraphrase) to prompts change model outputs; measure how often safety filters fail under perturbation.
* UG: Implement perturbation functions and run automated tests to compare outputs and flag filter failures.
* MSc: Design adversarial perturbations (character swaps, synonyms) and measure filter robustness; propose mitigation.
* Tools: Python text libraries, simple comparators (cosine similarity).
* Deliverable: robustness report + scripts.

7. **Low-Cost Sandboxing: Policy-Enforced LLM Proxy**

* What: A proxy server sits between client UI and an LLM, enforcing policies (rate limits, prompt length, banned tokens) and logging violations.
* UG: Implement proxy that redacts banned words and logs calls.
* MSc: Add dynamic policy updates, role-based access, and analytics dashboards for admins.
* Tools: FastAPI/Flask, simple SQLite, lightweight dashboard (Plotly or Streamlit).
* Deliverable: proxy code + deployment instructions.

8. **Synthetic Data Detector for Downstream Classifiers**

* What: Detect whether a training dataset contains synthetic examples (e.g., to prevent poisoning or bias). Students create synthetic data and see if detectors can spot it.
* UG: Create synthetic samples via a small generator and train a classifier on features (length, punctuation, perplexity).
* MSc: Explore feature engineering, ensemble detectors, and evaluate detection against paraphrased synthetic data.
* Tools: scikit-learn, transformers for perplexity estimates.
* Deliverable: detection notebook + evaluation metrics.

9. **Interactive User Study: How People Perceive Model Safety Interventions**

* What: Design a small experiment (ethics approved) to test how users react when an assistant refuses, deflects, or rewrites a query.
* UG: Build three UI variants (refuse, deflect politely, give safe alternative), recruit peers, collect qualitative feedback.
* MSc: Add statistical analysis of usability, sentiment analysis, and recommendations.
* Tools: Streamlit, Google Forms, basic stats (t-test, chi²).
* Deliverable: study report + anonymized data.

10. **Explainable Flagging: Why Was This Output Blocked?**

* What: When a moderator blocks model output, produce a short human-readable explanation (policy rule + example) for transparency.
* UG: Implement mapping from checks to canned explanations and a UI that surfaces them.
* MSc: Implement natural language explanations generated from features (e.g., “contains sexual content about minors” → provide features that led to block) and evaluate user trust.
* Tools: Simple templating, optional small model for explanation generation.
* Deliverable: explanation engine + user test.

11. **Lightweight Threat Score Card for Model Responses**

* What: Compute a composite “threat score” (privacy leakage, toxicity, misinformation risk) for each response and visualize it for moderators.
* UG: Define 3 metrics, implement scoring rules, and visualize with a dashboard.
* MSc: Calibrate scores using human annotations, implement weighting learned from data.
* Tools: Dash/Streamlit, basic scoring functions, human labels collected via classmates.
* Deliverable: dashboard + scoring rubric.

12. **Policy Update Simulator: How Fast Can a System Adapt?**

* What: Simulate the lifecycle of a safety policy change (e.g., new banned terms) and show propagation delays and failures in a distributed system of proxies/clients.
* UG: Implement a small mocked ecosystem (3 services) and show configuration propagation.
* MSc: Add automated tests, rollback strategies, and metrics for consistency and latency.
* Tools: Docker optional, simple HTTP services in Flask.
* Deliverable: simulation + analysis.

---

### Grading rubric (suggested)

* Implementation & reproducibility (30%): code runs, clear README, notebook/demo.
* Evaluation & experiments (30%): datasets, metrics, analysis (precision/recall/ROC or qualitative analysis).
* Report & reflection (25%): limitations, ethics, safety tradeoffs, extension ideas.
* Presentation & demo (15%): short live demo or video + slides.

---

### Ethical & safety guidance to give students (very important)

* Use simulated or public, non-sensitive datasets. Don’t craft real harmful prompts or produce actionable wrongdoing content.
* Obtain quick local ethics approval for any user studies and anonymize all data.
* Focus on defensive outcomes (detection, robustness, transparency) rather than providing ways to bypass protections.

---

### Low code/no code project ideas for medics (human centered design/HCI)

The following is inspired by an [HCI course from the University of Washington](https://courses.cs.washington.edu/courses/cse440/26wi/)

To design for students with little programming experience, the focus must shift from **back-end engineering** to **interaction design, ethics, and social contextualization.** 

Using a framework of **Low AI (WhatsUp)**, **Co-creative AI (Note Assist)**, and **AI-Intensive (Replika)**. 

These are designed to be built using "no-code" or "low-code" tools (like Voiceflow, Landbot, or simple GPT-wrappers) so students can focus on **Human-Centered Design (HCD)**.

---

### 1. "The Cultural Navigator" (Low AI / Resource-Based)

**Social Context:** First-generation immigrants or refugees navigating a new healthcare system (e.g., the NHS in the UK or Medicare in the US).

* **The Design Challenge:** Often, the barrier isn't just language; it’s a lack of "institutional literacy." Students design a chatbot that explains *how* the system works (e.g., "What is a GP?" or "How do I get a prescription?") using culturally relevant metaphors.
* **HCD Focus:** Students must interview someone from a different cultural background to understand their specific anxieties and "unwritten rules" of their home healthcare culture.
* **Tech Level:** Decision-tree logic. No GenAI required—just a well-mapped "knowledge path."

### 2. "Neuro-Transitioner" (Co-creative / Note Assist style)

**Social Context:** Neurodivergent students (ADHD/Autism) transitioning from high school to university life.

* **The Design Challenge:** "Executive function" is the hurdle. The chatbot doesn't just give advice; it helps the student *externalize* their thoughts. The AI suggests a breakdown of a complex medical or academic task (e.g., "Booking a therapy appointment"), and the student edits the steps to fit their energy levels.
* **HCD Focus:** Students focus on "the agency of the user." How can the AI suggest a plan without being "bossy" or overwhelming?
* **Tech Level:** Partial GenAI. The student designs prompts that take a goal and turn it into a checklist, which the user then modifies.

### 3. "The Grief Archivist" (AI-Intensive / Replika style)

**Social Context:** Individuals dealing with "ambiguous loss" (e.g., a family member with dementia) or long-term bereavement.

* **The Design Challenge:** A companion designed not to "fix" grief, but to witness it. The user can tell the bot stories about their loved one. The AI uses GenAI to reflect these stories back, helping the user curate a "digital memory book."
* **HCD Focus:** Ethical guardrails. Students must design the "exit strategy"—how does the bot handle it if the user becomes too dependent or expresses a mental health crisis?
* **Tech Level:** High GenAI involvement. Focuses on "Persona Design" and "Prompt Engineering" to ensure the bot’s tone is empathetic rather than clinical.

### 4. "Caregiver’s Handover" (Co-creative / Administrative)

**Social Context:** Unpaid family caregivers (e.g., a daughter looking after an elderly parent) who need to communicate with rotating professional nurses.

* **The Design Challenge:** Family caregivers are often exhausted and forget to relay small but vital details to pros. This bot "interviews" the caregiver at the end of their shift and generates a professional-grade "Handover Note" for the visiting nurse.
* **HCD Focus:** Understanding the "Power Dynamic." How does the bot bridge the gap between a "daughter’s emotional observation" and a "nurse’s clinical requirement"?
* **Tech Level:** GenAI used for "Style Transfer" (converting casual speech into structured medical observations).

### 5. "Safe-Space Simulator" (Low AI / Roleplay)

**Social Context:** LGBTQ+ youth in restrictive environments who are practicing "coming out" to a healthcare provider or asking for gender-affirming care.

* **The Design Challenge:** A "low-stakes" sandbox. The bot plays the role of a doctor. The user can practice their script. The bot provides feedback not on the *content*, but on how it felt (e.g., "You sounded very confident when you mentioned your symptoms").
* **HCD Focus:** Designing for "Psychological Safety." Students must research the specific microaggressions this community faces to ensure the "Simulated Doctor" isn't accidentally harmful.
* **Tech Level:** Scripted logic with "sentiment analysis" triggers.

---

### Pedagogical Tip: The "Social Context" Audit

Students to complete a **"Context Canvas"** before they touch any software:

1. **The Actor:** Who is the user (e.g., an elderly man living alone)?
2. **The Becoming:** Who does he want to *be*? (e.g., He doesn't want to be a "patient"; he wants to be "independent").
3. **The AI’s Role:** Is the AI a **Mirror** (Reflecting his thoughts), a **Scaffold** (Supporting his weaknesses), or a **Bridge** (Connecting him to a human doctor)?
4. **The Friction:** What is one thing the AI **should not** do to preserve the user's dignity?

By framing the project this way, the students are assessed on their **empathy and logic** rather than their ability to write Python code.

### Scientific agents for biomedical research

- Perform literature review
- Perform computational experiments
- Do sensitivity analysis and what-if scenarios
- Write reports

- for biomedical data, EHR data, genomic data. Example [scseq](https://github.com/sansomlab/scseq)

<!--

-->

### Foundation models for health

Building multi modal foundation models for health (electronic healthcare records data, omics data, etc.)

### Multi-agent systems for automated science

Building multi-agent systems, generative agents and generative AI systems for automated science. 

We will also look at applying these frameworks to other sectors (such as finance, economics, defence, environment, policy, etc.)

Look at:

https://github.com/AstroPilot-AI/Denario

https://github.com/CMBAgents/cmbagent

https://github.com/CMBAgents/cmbagent/blob/main/docs/notebooks/cmbagent_beta2_demo.ipynb

https://arxiv.org/pdf/2507.07257

https://www.aisi.gov.uk/work/long-form-tasks