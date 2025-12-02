# Take-Home Assignment: Cloud-Based PPG Signal Mini-Project

## Objective

Build a **small end-to-end pipeline** for a photoplethysmography (PPG)-like signal that:

1. Runs entirely in the **cloud** (Google Colab, AWS SageMaker notebook, or similar).
2. Includes **basic signal preprocessing** (filtering, feature extraction, visualization).
3. Trains a **simple ML model** for a clearly defined task (binary classification).
4. Exposes a **minimal interactive demo** (e.g., Gradio or simple widget) that runs in the cloud.
5. Is versioned and documented in a public **GitHub repository**.

This is not meant to be a perfect research project, but a realistic engineering exercise. 
Note: If you don't know how to set up cloud environment, use a jupyter notebook to deliver your result.(Cloud environment is a strong plus)

---

## Dataset

You are given a small synthetic dataset in:

`data/mock_ppg_dataset.csv`

Each row contains:

- `id` — segment ID  
- `signal` — a space-separated list of floating-point samples (PPG-like waveform)  
- `label` — either `clean` or `noisy`  

Sampling assumptions:

- Sampling frequency: **100 Hz**  
- Segment length: **8 seconds** (800 samples per row)  

---

## Tasks

### 1. Cloud Environment Setup

Use **one** of the following environments:

- Google Colab  
- AWS (SageMaker Studio / EC2 + Jupyter)  
- Any similar cloud notebook  

Requirements:

- The notebook must clone your GitHub repo (or access it).
- The notebook must load `mock_ppg_dataset.csv` from a URL or from the repo.
- It should run **end-to-end** without requiring local setup.

**Deliverable:**  
A link to a runnable cloud notebook (Colab / SageMaker / etc.).

---

### 2. Signal Preprocessing & Exploration

In your notebook, please:

1. **Load and parse** the `signal` column into 1D arrays.
2. **Visualize** at least 3–5 random segments (plot waveform vs. time).
3. Apply basic preprocessing, for example:
   - Band-pass filtering in a reasonable cardiac band (e.g., ~0.5–8 Hz).
   - Optional: detrend or normalize.
4. Compute at least **3–4 simple features** per segment, for example:
   - Mean and standard deviation  
   - Peak-to-peak amplitude  
   - Approximate heart rate (via peak detection)  
   - Signal energy or a simple entropy measure  

**Deliverables:**

- Plots of **raw** and **filtered** versions of a few segments.
- A brief explanation (1–2 short paragraphs) of your preprocessing choices.

---

### 3. Train a Simple ML Model

Define and solve a small **binary classification** task:

> Predict whether a segment is `clean` or `noisy` from the features you compute.

Minimum steps:

1. Split the data into train/validation (e.g., 80/20).
2. Use **either**:
   - A classical model: Logistic Regression, Random Forest, XGBoost/LightGBM, etc.; **or**
   - A very small neural network (optional, not required).
3. Train the model and report at least:
   - Accuracy  
   - F1 score  
4. Briefly discuss:
   - What seems to help the model?
   - Any signs of overfitting or limitations?

**Deliverables:**

- Training and evaluation code.
- Printed metrics.
- 2–3 sentences interpreting your results.

---

### 4. Minimal Interactive Demo

Create a simple demo that lets a user:

- Select a random validation segment **or**  
- Enter an `id` to inspect,

…and then shows:

- The waveform plot (filtered or both raw + filtered).  
- The model’s predicted label (`clean` / `noisy`).  

You can implement this **in any one** of these ways:

1. **Gradio or Streamlit app** inside Colab or on Hugging Face Spaces.  
2. A small widget / UI block in Colab (e.g., ipywidgets).  

**Deliverables:**

- The demo code in the notebook.
- If using Hugging Face Spaces or similar, a URL is appreciated (optional).

---

### 5. GitHub Repository & Documentation

Your public GitHub repo should include:

- `data/` (or a link to the dataset)  
- `notebooks/` — your main notebook  
- `src/` — optional helper modules (e.g., `preprocessing.py`, `features.py`, `model.py`)  
- `README.md` with:
  - Short project description  
  - How to run the notebook in the cloud  
  - How to use the demo  
  - Any assumptions or limitations  

**Deliverables:**

- GitHub repository URL  
- Clear instructions in `README.md`  

---

## What We Will Evaluate

We will **not** judge you on achieving perfect accuracy. Instead, we care about:

1. **Signal Processing Basics**
   - Reasonable choice of filters and parameters  
   - Clean, interpretable visualizations  
   - Sensible features  

2. **ML Pipeline Quality**
   - Proper train/validation split  
   - Appropriate model and metrics  
   - Awareness of overfitting / class balance  

3. **Cloud & Tooling**
   - End-to-end run in Colab / AWS / HF Spaces  
   - Clean repo with clear instructions  
   - Use of at least one modern tool (e.g., Gradio, HF Spaces, or similar)  

4. **Code Quality & Documentation**
   - Readability and structure  
   - Helpful comments and markdown  
   - Clear, concise explanations  

**Bonus (optional, not required):**

- Deploying a small app on Hugging Face Spaces or AWS.  
- Pushing the model to Hugging Face Hub and loading it in your demo.  
- Simple tests or sanity checks in the code.
