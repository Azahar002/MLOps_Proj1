# 🚗 Vehicle Insurance Prediction MLOps Project

A complete end-to-end **Machine Learning Operations (MLOps)** pipeline to train, evaluate, deploy, and monitor a vehicle insurance prediction model using **FastAPI, Docker, AWS, MongoDB Atlas, and GitHub Actions CI/CD**.

---

## 🔥 Highlights
- Clean, scalable project architecture
- Automated data ingestion and validation
- Modular training and prediction pipelines
- CI/CD with GitHub Actions & Docker
- Model versioning and cloud deployment on AWS EC2 & S3
- MongoDB Atlas integration for data storage

---

## 🚀 Quick Start
```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
```

---

## 📁 Project Setup
1. Generate directory structure by running:
```bash
python template.py
```
2. Setup `setup.py` and `pyproject.toml` to install as local package.
3. Verify packages installed:
```bash
pip list
```

---

## 🌐 MongoDB Atlas Setup
1. Create cluster on MongoDB Atlas
2. Create DB user & allow network access (`0.0.0.0/0`)
3. Get connection string and store in environment variable:
```bash
# Bash
export MONGODB_URL="<your_connection_string>"
```
4. Push local dataset to MongoDB via `notebook/mongoDB_demo.ipynb`

---

## 🧱 Data Ingestion
- Setup MongoDB connection and data fetch logic in `src/data_access/`
- Create `config_entity.py`, `artifact_entity.py`, and `components/data_ingestion.py`
- Trigger pipeline using:
```bash
python demo.py
```

---

## ✅ Data Validation | 🛠️ Data Transformation | 🎯 Model Training
1. Define schema in `config/schema.yaml`
2. Implement logic for each step under `components/`
3. Follow structured pipeline:
   - `constants/`
   - `config_entity/`
   - `artifact_entity/`
   - `component/`
   - `pipeline/`
   - `app.py`

---

## ☁️ AWS Setup (Model Evaluation & Pusher)
1. Create IAM user (name: `firstproj`) with **Admin Access**
2. Set environment variables:
```bash
export AWS_ACCESS_KEY_ID="..."
export AWS_SECRET_ACCESS_KEY="..."
```
3. Create S3 Bucket: `my-model-mlopsproj`
4. Write model push/pull logic in `aws_storage.py` and `s3_estimator.py`

---

## 🧠 Model Evaluation & Deployment
- Add logic in `model_evaluation.py` and `model_pusher.py`
- Build prediction pipeline and serve via `app.py`
- Add `static/` and `templates/` folders for frontend

---

## 🔄 CI/CD Pipeline (GitHub Actions)
### Setup
- Create `.github/workflows/aws.yaml`
- Add secrets:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `AWS_DEFAULT_REGION`
  - `ECR_REPO`

### GitHub Actions Steps
- Build Docker image → Push to ECR
- Connect to EC2 self-hosted runner → Run container

---

## 🐳 Dockerize & Deploy
1. Write `Dockerfile` and `.dockerignore`
2. Push image to ECR:
```bash
docker build -t <repo_url>:latest .
docker push <repo_url>:latest
```
3. On EC2:
```bash
sudo apt update && sudo apt install docker.io
./run.sh  # Run self-hosted GitHub runner
```

---

## 🌍 Accessing the App
1. Open port `5050` or `5080` in EC2 security group
2. Launch app:
```
http://<ec2-public-ip>:5080
```
3. Train model:
```
http://<ec2-public-ip>:5080/train
```

---

## 🤖 Tech Stack
- Python, FastAPI, Pandas, Scikit-learn
- MongoDB Atlas, AWS S3, AWS EC2, IAM
- Docker, GitHub Actions, ECR

---

## 💡 Recruiter Notes
This project is designed with **industry-grade MLOps practices**:
- Real-world cloud integrations (MongoDB, AWS)
- CI/CD workflow with GitHub Actions
- Containerized app with Docker
- Modular and maintainable Python codebase
- Scalable backend using FastAPI

---

## 📬 Let's Connect
**Shaik Azahar Mahaboob**  
GitHub: [github.com/Azahar002](https://github.com/Azahar002)

---

> "Build once. Deploy anywhere. Automate everything."

