# Tumour Classifier: interactive ML web app

**Prepared for: Arman Ilyas**

This app trains a logistic-regression classifier on scikit-learn's Breast Cancer Wisconsin dataset and serves it through FastAPI. Sliders send measurements to the API and the page presents a prediction plus each feature's contribution.

**Model:** Six features—mean radius, texture, area, smoothness, concavity, and symmetry—processed with `StandardScaler` and `LogisticRegression`.

```text
cancer-app/
├── train.py          trains the model and writes model.pkl + metadata.json
├── main.py           FastAPI backend and page server
├── requirements.txt
└── static/           index.html, style.css, app.js
```

## Run

```bash
python -m pip install -r requirements.txt
python train.py
python -m uvicorn main:app --reload --port 8000
```

## API

| Method | Path | Purpose |
|---|---|---|
| GET | `/api/info` | Slider ranges and model-quality metadata |
| POST | `/api/predict` | Accepts feature values and returns the prediction, probabilities, and feature effects |
| GET | `/api/health` | Health check |

## Deploy on Render

Use `cancer-app` as the root directory. Build with `pip install -r requirements.txt && python train.py`; start with `uvicorn main:app --host 0.0.0.0 --port $PORT`.

Educational demonstration only; not for medical use.
