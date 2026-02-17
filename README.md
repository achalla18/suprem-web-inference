# SuPreM CT Inference App

A simple web application for running abdominal CT segmentation using the SuPreM model.

Users can:
- Upload a CT scan (.nii.gz)
- Run AI inference using Docker and GPU
- Download the segmentation result

---

## Model

SuPreM  
https://huggingface.co/qicq1c/SuPreM

Docker image:
docker pull qchen99/suprem:v1

---

## Requirements

- Python 3.9+
- FastAPI
- Uvicorn
- Docker
- NVIDIA GPU

Install dependencies:
pip install fastapi uvicorn python-multipart

---

## Run the App

Start the server:
uvicorn app:app --reload

Open in browser:
http://127.0.0.1:8000

Upload a .nii.gz CT scan and click "Run Inference".

---

## Input Structure (auto-generated)

inputs/
└── casename00001/
    └── ct.nii.gz

---

## Output Structure

outputs/
└── casename00001/
    ├── combined_labels.nii.gz
    └── segmentations/

Main output file:
combined_labels.nii.gz

---
- GPU is required.
- This is an early-stage prototype.
- Only .nii.gz files are supported.
