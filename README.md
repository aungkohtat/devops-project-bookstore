# DevOps Project Bookstore
A sample full-stack bookstore app with React frontend and Flask backend, designed for DevOps learning, containerization, and Kubernetes deployment using OrbStack on macOS.

### Features
- React frontend UI
- Flask REST API backend
- PostgreSQL integration
- Dockerized for container deployment
- Kubernetes manifests for orchestration
- Tested with OrbStack Kubernetes on macOS

### Getting Started
1. clone repo
    ```
    git clone https://github.com/aungkohtat/devops-project-bookstore.git
    cd devops-project-bookstore
    ```

2. Run Frontend
   ```
    cd ui
    npm install
    npm start
   ```
3. Run Backend
   ```
   cd api
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   python3 main.py
  ```
4. Build Docker Images
   ```
    docker build -t akhlab/bookstore-frontend ./ui
    docker build -t akhlab/bookstore-backend ./api
    ```
5. Deploy to Kubernetes with OrbStack
  - Ensure OrbStack Kubernetes is running
  - Apply manifests in k8s/ folder:

    ```
    kubectl port-forward svc/bookstore-backend-service 5002:5002
    kubectl port-forward svc/bookstore-frontend-service 3000:3000
    ```
    - Access frontend at http://localhost:3000
    - Access backend at http://localhost:5002
