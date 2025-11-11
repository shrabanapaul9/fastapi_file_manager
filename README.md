# FastAPI File Management using PostgreSQL, MinIO, and Caching

##  Project Overview
This project implements a **complete file management system** using **FastAPI**, integrated with **PostgreSQL**, **MinIO**, and **FastAPI Caching**.  
It allows users to upload, retrieve, and merge files seamlessly while ensuring efficient storage and temporary in-memory caching for quick access.

Each uploaded file is securely stored in a MinIO bucket, with its metadata (file name and format) recorded in a PostgreSQL database.  
The project demonstrates how modern data engineering tools can build scalable backend systems for file storage and data management.

---

##  Features Implemented
1. **File Upload (POST /upload/)**  
   - Upload multiple CSV or Excel files.  
   - Validate file format before storage.  
   - Store metadata in PostgreSQL and file in MinIO.

2. **File Retrieval (GET /files/)**  
   - Fetch all uploaded files with their ID, name, and format.

3. **File Merge (GET /merge/)**  
   - Merge two selected files by `customer_id`.  
   - Use FastAPI cache to temporarily store the merged dataset.

4. **Save Merged Dataset (POST /save-merged/)**  
   - Retrieve cached data using a unique cache key.  
   - Save the merged dataset permanently to MinIO and update the database.

---

##  Tech Stack
- **Backend Framework:** FastAPI  
- **Database:** PostgreSQL  
- **Object Storage:** MinIO  
- **In-Memory Cache:** FastAPI Cache (InMemoryBackend)  
- **Language:** Python  
- **Tools:** Uvicorn, Pandas, SQLAlchemy

---

##  Installation & Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/shrabanapaul9/fastapi_file_manager.git
   cd fastapi_file_manager
