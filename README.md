# Predictive Maintenance with KNN on Azure Machine Learning

**Student:** Syeda Jovaria Nisar  
**Roll Number:** 1096

## Problem

Predict machine failure from sensor readings using the AI4I 2020 predictive maintenance dataset (UCI, CC BY 4.0).

## Approaches

1. **Notebook:** scikit-learn + MLflow — `notebooks/01_knn_notebook.ipynb`
2. **Automated ML:** KNN only — `automl/automl_results.md`
3. **Designer:** Execute Python Script — `designer/knn_designer_script.py`

## Results

| | Notebook | Automated ML | Designer |
|---|---:|---:|---:|
| Best K | N/A | N/A | 5 |
| Weights (uniform/distance) | N/A | N/A | distance |
| Scaler | StandardScaler | Chosen by AutoML | StandardScaler |
| Test recall (failure) | 0.3529 | 0.5339 | N/A |
| Test F1 (failure) | 0.3967 | 0.4538 | N/A |
| AUC | 0.6690 | 0.9022 | N/A |
| Code written | Most | None (optional SDK) | Small script |
| Time to set up (min) | N/A | N/A | N/A |
| Deployable to managed endpoint | Yes | Yes | No (classic components) |
| Best for | Full control, learning | Fast search, baseline | Visual teams, quick prototypes |

## Report Questions

### 1. Which approach gave the best recall on failures?

Automated ML gave the best failure recall at **0.5339**, compared with **0.3529** for the Notebook. The difference is noticeable, so Automated ML was better at identifying actual machine failures.

### 2. Which approach would you choose for a real factory project, and why?

I would choose **Automated ML as a strong starting point** because it can quickly compare models and provide a strong baseline. The selected model would then need to be carefully validated before deployment in a real factory environment.

### 3. Is 3.4% failures a problem for KNN?

Yes. The low failure rate creates a **class imbalance** problem, so KNN may favor the majority non-failure class. More failure data, a lower decision threshold, or class-weighted methods using another algorithm could help improve failure detection.

## Deployment

Managed online endpoint with deployment **blue** using VM **Standard_DS2_v2**.

Sample request: `deployment/sample-request.json`

Test script: `deployment/test_endpoint.py`

## What I Learned

I learned how to build and evaluate a KNN predictive maintenance model using three different Azure Machine Learning approaches. I compared a hands-on Notebook workflow with Automated ML and the visual Designer approach. I also learned how to deploy a trained model to a managed online endpoint and test it using a REST request. The project showed me why class imbalance and failure recall are important in predictive maintenance.

## Screenshots

See the `screenshots/` folder for project evidence.
