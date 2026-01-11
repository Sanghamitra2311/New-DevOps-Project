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
