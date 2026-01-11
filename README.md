# DevOps Flask Application

This project demonstrates a complete CI/CD pipeline for a simple Python Flask application using Google Cloud Platform services. The application is containerized with Docker and deployed to a Google Kubernetes Engine (GKE) cluster using Cloud Build.

## 🚀 Project Overview

The pipeline automates the following steps:

1.  **Build**: Creates a Docker image of the Flask application.
2.  **Push**: Uploads the image to Google Container Registry (GCR) or Artifact Registry.
3.  **Deploy**: Updates the GKE cluster with the new image using Kubernetes manifests.

## 🛠️ Technology Stack

- **Language**: Python 3
- **Framework**: Flask
- **Containerization**: Docker
- **CI/CD**: Google Cloud Build
- **Orchestration**: Google Kubernetes Engine (GKE)

## 📂 Project Structure

- `app.py`: The main Flask application entry point.
- `Dockerfile`: Instructions to build the Docker container image.
- `cloudBuild.yaml`: Configuration for Google Cloud Build triggers and steps.
- `deployment.yaml`: Kubernetes Deployment manifest for GKE.
- `requirements.txt`: Python dependencies.

## 💻 Local Development

To run the application locally:

1.  **Prerequisites**: Ensure Python and `pip` are installed.
2.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```
3.  **Run Application**:
    ```bash
    python app.py
    ```
    The app will be accessible at `http://localhost:5000`.

## ☁️ Deployment

The deployment is managed via **Google Cloud Build**.

### Prerequisites

- A Google Cloud Project with Billing enabled.
- APIs enabled: Cloud Build, Kubernetes Engine, Container Registry/Artifact Registry.
- A running GKE cluster (configured in `cloudBuild.yaml`).

### Triggering a Build

The build process is defined in `cloudBuild.yaml`. It performs the following:

1.  Builds the Docker image tagged with the Project ID.
2.  Pushes the image to the registry.
3.  Deploys the image to the specified GKE cluster using `gke-deploy`.

_Note: Ensure your `cloudBuild.yaml` variables (Cluster Name, Zone, Namespace) match your GCP environment._

## Sample Screenshots:

**Artifacts Registory**
<img width="1368" height="611" alt="image" src="https://github.com/user-attachments/assets/da42f79c-0384-4d92-9731-668cd15f0a7b" />

**Cloud Build Logs**
<img width="1904" height="485" alt="image" src="https://github.com/user-attachments/assets/1d83a68b-434a-4313-990d-d32774e93ac7" />
<img width="1614" height="688" alt="image" src="https://github.com/user-attachments/assets/0e7df1b8-5e52-44a9-b695-4997ecbb3b9b" />
<img width="1614" height="688" alt="image" src="https://github.com/user-attachments/assets/e9d13996-4a2e-4e5c-8c33-f18ebd202a26" />

**Triggers**
<img width="1597" height="386" alt="image" src="https://github.com/user-attachments/assets/297342f9-3d91-4eee-a502-2861504fdda0" />

**Cluster & workloads for Dev & Prod env's**
<img width="1564" height="376" alt="image" src="https://github.com/user-attachments/assets/464674da-ada4-4f75-b12b-b154e9131074" />
<img width="1898" height="463" alt="image" src="https://github.com/user-attachments/assets/11231eaa-f2be-4b68-8124-167f28fdc5d2" />

**Services for Dev, Prod namespaces**
<img width="1618" height="563" alt="image" src="https://github.com/user-attachments/assets/afc7e689-6848-4495-9bf8-5910756d3577" />

**Website after Deployment**
<img width="1331" height="523" alt="image" src="https://github.com/user-attachments/assets/fab92cb4-167b-4b3a-92e0-c9c139fe5bd5" />











