# Eye Disease Classification Using CNN Architectures

A comparative deep learning project evaluating modified **VGG-16, AlexNet, and GoogLeNet** architectures for classifying retinal images into four categories: Cataract, Diabetic Retinopathy, Glaucoma, and Normal.

## Overview

Eye diseases can lead to serious vision impairment if they are not detected and managed appropriately. This project explores the use of convolutional neural networks (CNNs) for automated classification of retinal images.

The main objective is to compare three CNN architectures and evaluate their classification accuracy, training duration, and potential computational efficiency. Rather than relying entirely on standard pretrained models, the project uses modified architectures with reduced layers and parameters to explore a balance between model complexity and predictive performance.

This repository contains the project notebook and final report.

## Objectives

- Implement and compare modified VGG-16, AlexNet, and GoogLeNet architectures.
- Classify retinal images into four eye-condition categories.
- Evaluate model performance using test accuracy and classification metrics.
- Explore methods to reduce model complexity and computational requirements.
- Compare training duration and predictive performance across architectures.

## Dataset

The project report describes a dataset containing **4,217 images** across four classes:

| Class | Description |
|---|---|
| Cataract | Retinal/eye images labelled as cataract |
| Diabetic Retinopathy | Images labelled as diabetic retinopathy |
| Glaucoma | Images labelled as glaucoma |
| Normal | Images labelled as normal |

The dataset was used to train and evaluate the models. The original dataset is not included in this repository.

**Dataset source:** The report references the *Eye Diseases Classification* dataset by Gunavenkat Doddi on Kaggle. Please refer to the original dataset page for access and applicable licensing terms.

## Models Compared

### 1. Modified VGG-16
A VGG-style CNN modified by reducing layers and parameters. It achieved the highest reported test accuracy among the three evaluated models.

### 2. Modified AlexNet
An AlexNet-style CNN adapted for the four-class classification task. It achieved competitive accuracy with a substantially shorter reported training duration than VGG-16.

### 3. Modified GoogLeNet
A GoogLeNet-style CNN adapted for the same classification task. Its results provide a third point of comparison for accuracy and training efficiency.

## Methodology

The project uses the following general workflow:

1. Load and prepare the retinal image dataset.
2. Preprocess images for model input.
3. Split the data into training, validation, and test subsets.
4. Train the three modified CNN architectures.
5. Apply data augmentation and training-control techniques.
6. Use hold-out validation, early stopping, and dynamic learning-rate reduction.
7. Evaluate the trained models on the test set.
8. Compare test accuracy, class-level metrics, and training duration.

The report identifies the Adam optimizer and a learning rate of `0.0001` for the best-performing VGG-16 configuration, with a batch size of `32` and `50` epochs.

Refer to the notebook and report for the implementation details and experimental setup.

## Reported Results

The following results are taken from the project report.

| Model | Test accuracy | Reported training duration |
|---|---:|---:|
| Modified VGG-16 | 87.50% | 6 hours 34 minutes |
| Modified AlexNet | 84.68% | 13 minutes 27 seconds |
| Modified GoogLeNet | 80.73% | 30 minutes 2 seconds |

### Key observations

- **VGG-16 achieved the highest reported test accuracy** at 87.50%.
- AlexNet achieved 84.68% accuracy with the shortest reported training duration.
- GoogLeNet achieved 80.73% test accuracy in the reported experiments.
- The results illustrate a trade-off between predictive performance and training cost for the tested configurations.

These results represent the experiments documented in the project report. They should not be interpreted as guarantees of performance on other datasets or clinical populations.

## Repository Structure

```text
eye-disease-classification/
├── eye_disease_classification.ipynb
├── project-report.pdf
├── README.md
├── .gitignore
└── .gitattributes
```

- `eye_disease_classification.ipynb` — notebook containing model development, training, evaluation, and prediction code.
- `project-report.pdf` — detailed academic report, methodology, experimental results, and references.
- `.gitignore` — excludes selected local and generated files from version control.
- `.gitattributes` — Git file-handling configuration.

## Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab
- The deep learning and data-processing libraries imported by the notebook
- An authorized copy of the dataset

The exact package versions and hardware requirements should be confirmed from the original development environment.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Akash-X1/eye-disease-classification.git
   cd eye-disease-classification
   ```

2. Create and activate a virtual environment if desired:

   ```bash
   python -m venv .venv
   ```

   Windows:

   ```bash
   .venv\Scripts\activate
   ```

   macOS/Linux:

   ```bash
   source .venv/bin/activate
   ```

3. Install Jupyter:

   ```bash
   python -m pip install jupyter
   ```

4. Install the additional dependencies required by the notebook. Review its import cells and use the package versions compatible with the original implementation.

5. Obtain the dataset from its authorized source and configure the dataset path in the notebook.

6. Launch Jupyter:

   ```bash
   jupyter notebook
   ```

7. Open `eye_disease_classification.ipynb` and follow the notebook cells in order.

**Note:** The notebook may contain a machine-specific dataset path. Update it to match your local dataset location before executing the code.

## Evaluation

The project report includes test accuracy, class-level precision, recall, F1-score, and other evaluation material. These metrics help compare model behaviour across the four image classes.

For reproducibility, use the same dataset split, preprocessing steps, model configurations, and evaluation procedure documented in the report.

## Limitations

- The models were evaluated on a specific dataset and may not generalize to different populations, imaging devices, or clinical settings.
- Performance depends on dataset quality, class distribution, preprocessing, and training configuration.
- Training duration depends on the hardware and software environment.
- The repository does not currently include the original dataset or verified trained model checkpoints.
- The reported results have not been independently reproduced as part of this repository preparation.

**This project is for academic and research purposes only. It is not a clinically validated diagnostic system and must not be used as a substitute for assessment by a qualified healthcare professional.**

## Future Improvements

Potential future work includes:

- Testing on independent external datasets.
- Improving reproducibility through pinned dependency versions and fixed random seeds.
- Comparing model size, inference latency, and memory usage.
- Adding a documented inference script and example predictions.
- Exploring model compression and deployment on resource-constrained hardware.

## Team and Contributions

This was completed as a group academic project.

The report lists the following project members:

- Akash Kumar
- Amaan Shaikh
- Rasesh Ramperand

The GitHub commit history reflects repository activity and does not necessarily represent the full contribution history of every team member.

## References

Consult `project-report.pdf` for the full literature review and bibliography, including the cited dataset reference:

Doddi, Gunavenkat. *Eye Diseases Classification*. Kaggle dataset, 2022. https://www.kaggle.com/datasets/gunavenkatdoddi/eye-diseases-classification

