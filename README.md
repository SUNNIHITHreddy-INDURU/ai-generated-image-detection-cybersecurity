# Lightweight and Robust AI-Generated Image Detection for Cybersecurity Applications

This project investigates deep learning methods for detecting whether an image is real or AI-generated. The project is motivated by cybersecurity use cases such as fake social profile creation, phishing campaigns, misinformation, online fraud, and digital evidence manipulation.

## Dataset

The project uses the CIFAKE dataset from Kaggle:

https://www.kaggle.com/datasets/birdy654/cifake-real-and-ai-generated-synthetic-images

The dataset contains 120,000 images:
- 60,000 REAL images
- 60,000 FAKE AI-generated images

The dataset is not included in this repository due to size. It can be downloaded directly from Kaggle using the Kaggle API.

## Models

The following models are implemented and evaluated:

- Vanilla CNN baseline
- MobileNetV2
- EfficientNetB0
- Robust EfficientNetB0 with augmentation-aware training

## Robustness Testing

The models are evaluated under clean and transformed image conditions:

- JPEG compression
- Gaussian blur
- Gaussian noise
- Downscale-upscale resizing
- Brightness reduction

## Main Results

Clean test results:

| Model | Accuracy | F1-score | ROC-AUC |
|---|---:|---:|---:|
| Vanilla CNN | 0.9541 | 0.9543 | 0.9913 |
| MobileNetV2 | 0.9701 | 0.9701 | 0.9961 |
| EfficientNetB0 | 0.9831 | 0.9830 | 0.9983 |
| Robust EfficientNetB0 | 0.9821 | 0.9820 | 0.9986 |

Robust EfficientNetB0 achieved strong clean-image performance and substantially improved robustness under image transformations.

## How to Run

1. Open the notebook in Google Colab.
2. Upload your Kaggle API key `kaggle.json`.
3. Run the notebook cells in order.
4. The notebook downloads the dataset, trains the models, evaluates robustness, and saves result tables.

## Requirements

The project was developed using:

- Python
- PyTorch
- Torchvision
- Scikit-learn
- NumPy
- Pandas
- Matplotlib
- Google Colab A100 GPU

## Reproducibility

All experiments can be reproduced by running the notebook from start to finish. The trained model files are not included because they can be regenerated from the notebook.

## Project Title

Lightweight and Robust AI-Generated Image Detection for Cybersecurity Applications
