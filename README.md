# Heart Disease Prediction

An end-to-end machine learning project for predicting the presence of heart disease using clinical features. Built with a modular MLOps architecture covering data ingestion, transformation, model training, and evaluation — with MLflow experiment tracking and a Flask web interface for live predictions.

## Features

- Modular pipeline: data ingestion → transformation → training → evaluation
- Classification model with accuracy, precision, recall, and F1 score metrics
- MLflow integration for experiment tracking and model registry
- DVC for pipeline versioning and data reproducibility
- Flask web UI for real-time predictions
- Dockerized for easy deployment

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| Scikit-learn | Classification models & preprocessing |
| Pandas / NumPy | Data manipulation |
| MLflow | Experiment tracking & model registry |
| DVC | Pipeline & data versioning |
| Flask | Web application & prediction API |
| Docker | Containerization |

## Project Structure

```
heart-disease-prediction/
├── src/Heart/
│   ├── components/         # Data ingestion, transformation, training, evaluation
│   ├── pipeline/           # Training & prediction pipelines
│   ├── utils/              # Shared utility functions
│   ├── exception.py        # Custom exception handling
│   └── logger.py           # Logging setup
├── Artifacts/              # Generated model & data artifacts
├── mlruns/                 # MLflow experiment logs
├── Notebook_Experiments/   # EDA & training notebooks
├── templates/              # Flask HTML templates
├── static/                 # CSS styles
├── app.py                  # Flask web application
├── setup.py                # Package setup
├── dvc.yaml                # DVC pipeline stages
├── Dockerfile              # Docker image definition
└── requirements.txt        # Python dependencies
```

## Getting Started

### Prerequisites

- Python 3.8+
- Docker (optional)

### Installation

```bash
git clone https://github.com/smunir25/general-ai-heart-disease-prediction.git
cd general-ai-heart-disease-prediction
pip install -r requirements.txt
```

### Run Training Pipeline

```bash
python src/Heart/pipeline/Training_pipeline.py
```

Or using DVC:

```bash
dvc repro
```

### Run the Web App

```bash
python app.py
```

Visit `http://localhost:5000` and enter patient data to get a prediction.

### Docker

```bash
docker build -t heart-disease-prediction .
docker run -p 5000:5000 heart-disease-prediction
```

## Input Features

| Feature | Description |
|---------|-------------|
| `age` | Age of the patient |
| `sex` | Sex (1 = male, 0 = female) |
| `cp` | Chest pain type (0–3) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl (1 = true) |
| `restecg` | Resting ECG results (0–2) |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina (1 = yes) |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment |
| `ca` | Number of major vessels (0–3) |
| `thal` | Thalassemia type (0–3) |

## Evaluation Metrics

- Accuracy, Precision, Recall, F1 Score — all logged to MLflow per run

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
