# Diabetes Predictor: interactive web app

**Prepared for: Arman Ilyas**

This app serves the included logistic-regression model (`Mymdoel.pkl`) through FastAPI and provides a live, slider-based prediction interface.

```text
diabetes-app/
├── Mymdoel.pkl       trained LogisticRegression model
├── main.py           FastAPI backend and page server
├── requirements.txt
└── static/           index.html, style.css, app.js
```

## Run

```bash
python -m pip install -r requirements.txt
python -m uvicorn main:app --reload --port 8000
```

Open `http://localhost:8000` for the app or `http://localhost:8000/docs` for the API documentation.

| Method | Path | Purpose |
|---|---|---|
| GET | `/api/info` | Slider ranges and model information |
| POST | `/api/predict` | Accepts six input values and returns a label, probability, and per-input effects |
| GET | `/api/health` | Health check |

## Deploy on Render

Use `diabetes-app` as the root directory. Build with `pip install -r requirements.txt`; start with `uvicorn main:app --host 0.0.0.0 --port $PORT`.

Educational demonstration only; not medical advice.
