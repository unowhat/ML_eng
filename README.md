Getting Started (For Candidates)

Clone this repo

git clone https://github.com/<ORG_OR_USER>/ppg-cloud-ml-takehome.git
cd ppg-cloud-ml-takehome


Open the assignment descriptions

PPG assignment: assignments/ppg_assignment.md

CNN assignment: assignments/cnn_assignment.md

Environment options

You may use any of:

Google Colab

AWS SageMaker or a Jupyter notebook on an EC2 instance

Another cloud notebook environment you are comfortable with

You do not need to run anything locally; however, running locally with a venv is also fine if that’s your preference.

Installing Dependencies (Optional Local Setup)

If running locally:

python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt


Core Python requirements are listed in requirements.txt.

PPG Assignment Summary

See: assignments/ppg_assignment.md

At a high level, you will:

Work in a cloud notebook (Colab, SageMaker, etc.).

Load and parse data/mock_ppg_dataset.csv.

Perform basic signal preprocessing (e.g., band-pass filtering, normalization).

Extract simple features (mean, std, peak-to-peak amplitude, approximate heart rate, etc.).

Train a small binary classifier (e.g., Logistic Regression) to predict clean vs noisy.

Build a minimal interactive demo (e.g., with Gradio or widgets) to visualize a segment and show the prediction.

Push your work to a public GitHub repo and provide a link to your cloud notebook.

CNN Assignment Summary

See: assignments/cnn_assignment.md

At a high level, you will:

Implement a tiny CNN in PyTorch for 32×32 RGB images with:

One Conv2d + ReLU block.

A fully connected layer mapping to 10 classes.

Verify output shapes using a simple test() function.

Manually compute and report the number of parameters.

Optionally extend the model with:

Adaptive pooling for dynamic input size.

Programmatic parameter counting.

This assignment is focused on basic PyTorch + CNN fundamentals, not on training a full CIFAR-10 model.
