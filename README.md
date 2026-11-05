# Introduction to AI: Lab Works

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.9.1-F7931E?logo=scikitlearn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)

Complete lab portfolio for **Introduction to AI**, BS Robotics & AI, University of Lahore.

> **Prepared for:** Arman Ilyas  
> **Scope:** Labs 02–07, practice work, and two FastAPI-based machine-learning demos.

This portfolio demonstrates a reproducible path from data collection and feature engineering to model evaluation and locally served applications.

## Included applications

| App | Model | Purpose |
|---|---|---|
| [Diabetes Predictor](diabetes-app/) | Logistic regression, 6 clinical inputs | Interactive prediction interface with feature effects |
| [Tumour Classifier](cancer-app/) | Logistic regression, 6 cell-nucleus features | Interactive classification interface with model explanations |

## Pipeline covered

```text
Scrape/collect → Features → EDA → Train → Evaluate → Serve (API) → Deploy
   Lab 2          Lab 2–3    Lab 2    Lab 4    Lab 4      Lab 6, apps
```

## Contents

| Folder | What it covers | Key tools |
|---|---|---|
| [`lab-02-web-scraping-eda/`](lab-02-web-scraping-eda/) | Scrape articles, engineer NLP features, EDA, TF-IDF | requests, BeautifulSoup, spaCy, TextBlob, seaborn |
| [`lab-03-text-image-features/`](lab-03-text-image-features/) | Turn text and images into numeric features | CountVectorizer, Pillow, NumPy |
| [`lab-04-regression-logistic/`](lab-04-regression-logistic/) | Linear and logistic regression, evaluation, cross-validation | scikit-learn, pandas, matplotlib |
| [`lab-06-fastapi-diabetes-api/`](lab-06-fastapi-diabetes-api/) | Diabetes model served as a REST API | FastAPI, Pydantic |
| [`lab-07-cnn-kernel-from-scratch/`](lab-07-cnn-kernel-from-scratch/) | CNN forward pass: convolution, ReLU, dense layer, softmax | NumPy |
| [`cancer-app/`](cancer-app/) | Full-stack ML app with per-feature explanations | FastAPI, JavaScript frontend |
| [`diabetes-app/`](diabetes-app/) | Full-stack ML app with prediction history | FastAPI, JavaScript frontend |
| [`practice/`](practice/) | Practice datasets and notebooks | pandas |

Labs 1 and 5 are not included in this repository.

## Run locally

Run each app from its own folder:

```bash
cd diabetes-app      # or cancer-app
python -m pip install -r requirements.txt
python train.py      # cancer-app only
python -m uvicorn main:app --reload --port 8000
```

Open `http://localhost:8000` for the app and `http://localhost:8000/docs` for the API documentation.

## Notes

- The saved `.pkl` models require the scikit-learn version specified in each app's `requirements.txt`.
- These educational projects are demonstrations only and do not provide medical advice or clinical diagnoses.

## Student

**Arman Ilyas**
