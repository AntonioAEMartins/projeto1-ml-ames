### Ames Housing — Sale Price Prediction (EDA + FastAPI)

Authors: Antônio Martins and Rodrigo Anciães

### Goal

Predict residential sale prices (target: `SalePrice`) using the Ames Housing dataset (2930 observations, 82 variables). The notebooks cover data loading, EDA, preprocessing/feature engineering, and regression modeling aimed at minimizing prediction error.

### Project Structure

```
projeto1-ml-ames/
  docs/
    DataDocumentation.txt        # Official Ames dataset documentation
  notebooks/
    01_reading_raw_data.ipynb    # Data loading and basic exploration
    02_analysis_and_preprocessing.ipynb
    03_linear_regression_modeling.ipynb
    projeto1-feature-eng.ipynb   # Deep dive + feature simplification
    projeto1.ipynb               # End-to-end modeling experiments
    fast_deploy.py               # FastAPI app for serving predictions
  environment.yml                # Reproducible conda environment
  README.md
```

### Deployment (FastAPI)

- App: `notebooks/fast_deploy.py` (loads `stack_reg.pkl`)
- Endpoints: `GET /` (health/info), `POST /predict` (predict sale price)
- Requirements (add to the conda env):
  ```bash
  pip install fastapi uvicorn
  ```
- Start from repository root (model file placed alongside the app):
  ```bash
  uvicorn fast_deploy:app --reload --host 0.0.0.0 --port 8000 --app-dir notebooks
  ```
- Deployed demo (Hugging Face Space):
  - Space page: [https://huggingface.co/spaces/antonioaem/machine-learning-insper-projeto1](https://huggingface.co/spaces/antonioaem/machine-learning-insper-projeto1)
  - Live app: [https://antonioaem-machine-learning-insper-projeto1.hf.space/](https://antonioaem-machine-learning-insper-projeto1.hf.space/)