# KubeFlow

# Cloud-Native Application on Google Cloud Platform (GCP)

## Project Architecture 

![image](https://github.com/kishore7403/KubeFlow/assets/48860055/86036277-314a-415b-9b80-0b46a206766d)


This project demonstrates the creation of a cloud-native application on the Google Cloud Platform (GCP) using containerization, CI/CD pipelines, and Google Kubernetes Engine (GKE). The application consists of two microservices that interact with each other, providing file storage and product calculation capabilities.

## Table of Contents
- [Project Overview](#project-overview)
- [Microservices](#microservices)
- [CI/CD Pipeline](#ci/cd-pipeline)
- [GKE Cluster](#gke-cluster)
- [Persistent Volume (PV)](#persistent-volume-pv)
- [API Endpoints](#api-endpoints)

## Project Overview

The goal of this project is to build a cloud-native application on GCP with the following key components:

- **Microservices:** Two microservices are developed to interact with each other. These microservices are containerized using Docker and deployed in GKE.

- **CI/CD Pipeline:** CI/CD pipelines are set up using GCP tools, including Cloud Build, to automate the build and deployment of microservices.

- **GKE Cluster:** A GKE cluster is provisioned using Terraform with specific configurations to save costs. It consists of a single node and a persistent disk.

- **Persistent Volume (PV):** A persistent volume is attached to the GKE cluster, allowing the microservices to read and write files.

- **API Endpoints:** RESTful API endpoints are created for microservices to store files and calculate product totals.

- **Deployment and Exposing Services:** YAML files are used to deploy microservices and expose them as services to the internet.

## Microservices

- **Container 1:** This microservice is responsible for storing files to the persistent volume, validating input JSON requests, and communicating with Container 2.

- **Container 2:** This microservice accesses the persistent volume, calculates the total of a product from a given file, and communicates with Container 1.

## CI/CD Pipeline

- Cloud Source Repository is used to store the source code of both microservices.
- Cloud Build is used to automate the build and deployment process whenever new code commits are pushed.

## GKE Cluster

- A GKE cluster is created using Terraform with specific configurations to save costs:
  - Single node.
  - Container-Optimized OS with containers.
  - E2 series, e2-micro machine type.
  - Standard persistent disk.

## Persistent Volume (PV)

- A persistent volume is attached to the GKE cluster and mounted at `/Kisgoreganesh_PV_dir`.

## API Endpoints

- `/store-file`: Container 1 stores files in the persistent volume based on JSON input.
- `/calculate`: Container 2 calculates the total of a product from a given file.


Feel free to explore the project and use it as a reference for building your own cloud-native applications on GCP.
