# Getting Started (For Candidates)

## 1. Clone this repository

```bash 
git clone https://github.com/unowhat/ML_eng.git
cd ppg-cloud-ml-takehome
```
## 2. Open the assignment descriptions

-PPG assignment: assignments/ppg_assignment.md

-CNN assignment: assignments/cnn_assignment.md

## 3. Environment Options

You may use any of the following environments:

-Google Colab

-AWS SageMaker or a Jupyter notebook on an EC2 instance

-Any cloud-based notebook environment you prefer

You do not need to run anything locally.
However, using a local virtual environment is also acceptable.

# PPG Assignment Summary

See: `assignments/ppg_assignment.md`

### At a high level, you will:

- Work in a cloud notebook (Colab, SageMaker, etc.)
- Load and parse `data/mock_ppg_dataset.csv`
- Perform basic signal preprocessing:
  - band-pass filtering
  - normalization
- Extract simple features such as:
  - mean
  - standard deviation
  - peak-to-peak amplitude
  - approximate heart rate
- Train a binary classifier to predict clean vs noisy
- Build a minimal interactive demo (Gradio or Colab widgets)
- Push your work to a public GitHub repo and provide a link to your cloud notebook

---

# CNN Assignment Summary

See: `assignments/cnn_assignment.md`

### At a high level, you will:

- Implement a tiny CNN in PyTorch for 32×32 RGB images, including:
  - One Conv2d + ReLU block
  - One fully connected layer mapping to 10 classes
- Verify output shapes using a simple `test()` function
- Manually compute and report the number of trainable parameters
