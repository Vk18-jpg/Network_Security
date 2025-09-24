# 🚀 End-to-End ML Pipeline for Network Security  

This project implements an **end-to-end machine learning pipeline** for automating data ingestion, preprocessing, model training, and deployment in a cloud environment. It is designed to detect and prevent network security threats using a scalable, production-ready workflow.  

---

## 🔹 Features  
- **Data Ingestion:** Fetches raw data from **MongoDB**.  
- **Data Validation:** Automated schema checks and drift detection to ensure data quality.  
- **Preprocessing:**  
  - Missing value handling with **KNN Imputer**  
  - Class imbalance correction using **SMOTE**  
  - Train/test split with leakage prevention  
- **Artifact Management:**  
  - Transformed data saved as **NumPy arrays**  
  - Preprocessing pipeline stored as **Pickle files** for reuse  
- **Model Training & Packaging:** Trains ML models using **Scikit-Learn**, packages best model with **FastAPI** for inference.  
- **Containerization:** Application containerized with **Docker** for reproducibility.  
- **CI/CD:** Automated workflow using **GitHub Actions** to:  
  1. Run tests and linting  
  2. Build Docker images and push to **AWS ECR**  
  3. Deploy on **AWS EC2** with a self-hosted runner  
- **Cloud Storage:** ML artifacts and logs stored in **AWS S3** for versioning.  

---

## 🔹 Architecture  

```mermaid
flowchart LR
    A[MongoDB - Raw Data] --> B[Data Validation & Preprocessing]
    B --> C[Train/Test Split]
    C --> D[Model Training & Evaluation]
    D --> E[FastAPI Model Service]
    E --> F[Docker Container]
    F --> G[AWS ECR - Image Registry]
    G --> H[AWS EC2 - Deployment]
    D --> I[AWS S3 - Store Artifacts]
