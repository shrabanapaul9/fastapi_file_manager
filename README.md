# FastAPI File Management using PostgreSQL, MinIO, and Caching

## Project Overview
This project implements a **complete file management system** using **FastAPI**, integrated with **PostgreSQL**, **MinIO**, and **FastAPI Caching**. It allows users to upload, retrieve, and merge files seamlessly while ensuring efficient storage and temporary in-memory caching for quick access. Each uploaded file is securely stored in a MinIO bucket, with its metadata (file name and format) recorded in a PostgreSQL database. The project demonstrates how modern data engineering tools can build scalable backend systems for file storage and data management.

---

## Features Implemented

### 1. **File Upload (POST /upload/)**
- Upload multiple CSV or Excel files.
- Validate file format before storage.
- Store metadata in PostgreSQL.
- Store file securely in MinIO.

### 2. **File Retrieval (GET /files/)**
- Fetch all uploaded files.
- Returns file ID, file name, and file format.

### 3. **File Merge (GET /merge/)**
- Merge two selected files by `customer_id`.
- Uses FastAPI in-memory cache to temporarily store the merged dataset.
- Provides a unique cache key for retrieval.

### 4. **Save Merged Dataset (POST /save-merged/)**
- Retrieve merged data from cache using its key.
- Save the merged file permanently to MinIO.
- Update metadata in PostgreSQL.

---

## Tech Stack
- **Backend Framework:** FastAPI
- **Database:** PostgreSQL
- **Object Storage:** MinIO
- **In-Memory Cache:** FastAPI Cache (InMemoryBackend)
- **Language:** Python
- **Tools:** Uvicorn, Pandas, SQLAlchemy

---

# ZIP File Included — `FastAPI_Project_Shrabana.zip`

This ZIP file contains the **complete backend project code** arranged in a clean and production-ready structure.

### ZIP Contents:
app/                → Main FastAPI application
data/               → Sample datasets
minio_data/         → Example MinIO bucket files
requirements.txt    → List of dependencies

### Inside `app/` folder:
- main.py → FastAPI entry point
- routers/ → Upload, retrieval, merge, save APIs
- services/ → MinIO client, caching logic, DB operations
- models/ → Pydantic schemas
- config/ → Configuration for PostgreSQL & MinIO
- utils/ → Helper functions

---

## Installation & Setup

### 1. Clone the repository:
git clone https://github.com/shrabanapaul9/fastapi_file_manager.git
cd fastapi_file_manager

### 2. Install dependencies:
pip install -r requirements.txt

### 3. Start MinIO using Docker:
docker run -p 9000:9000 -p 9001:9001 \
  -e MINIO_ROOT_USER=minioadmin \
  -e MINIO_ROOT_PASSWORD=minioadmin \
  minio/minio server /data --console-address ":9001"

### 4. Start the FastAPI server:
uvicorn app.main:app --reload

### 5. Open API Documentation:
http://127.0.0.1:8000/docs

---

## Project Report
The repository includes a detailed PDF report:
ShrabanaPaul_FastAPI_FileManagement_Report.pdf

---

## Author
**Shrabana Paul**
Autumn Internship Project – FastAPI File Management System

