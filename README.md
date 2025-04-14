# 🚀 Day 5: Kubernetes Cluster

![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.21-blue)
![Minikube](https://img.shields.io/badge/Minikube-v1.23-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

This repository showcases the work completed in setting up and managing Kubernetes clusters using Minikube. The focus is on deploying a **Hello World** application using **Pods**, **ReplicaSets**, and **Deployments**, with exposure through a **NodePort** service.

> **Note**: The configurations for Pods, ReplicaSets, and Deployments are organized into separate folders to ensure modularity, scalability, and ease of maintenance. This approach aligns with Kubernetes best practices, enabling independent management and scaling of specific components.

---

## 📁 Folder Structure

- **`PODS/`** – Contains Pod definitions and NodePort service configurations  
    - Files: `pod.yaml`, `service.yaml`, `README.md`
- **`REPLICASET/`** – Contains ReplicaSet definitions and NodePort service configurations  
    - Files: `replicaset.yaml`, `service.yaml`, `README.md`
- **`DEPLOYMENTS/`** – Contains Deployment definitions for scaling and auto-healing, along with NodePort service configurations  
    - Files: `deployment.yaml`, `service.yaml`, `README.md`

---

## 🚀 How to Run

1. **Start Minikube Cluster**
     ```bash
     minikube start
     ```

2. **Apply Configurations**
     Navigate to each folder (`PODS/`, `REPLICASET/`, `DEPLOYMENTS/`) and apply the respective YAML files:

     ```bash
     kubectl apply -f pods/pod.yaml
     kubectl apply -f replicaset/replicaset.yaml
     kubectl apply -f deployment/deployment.yaml
     ```

3. **Verify Resources and Access the Application**
     - Check the status of Pods and Services:
         ```bash
         kubectl get pods
         kubectl get svc
         ```
     - Access the application via the NodePort service:
         ```bash
         minikube service my-service --url
         ```

---

## 📸 Screenshots

- **Pods and Services**: Refer to the `PODS/` folder for screenshots.
- **ReplicaSet**: Refer to the `REPLICASET/` folder for screenshots.
- **Deployment**: Refer to the `DEPLOYMENTS/` folder for screenshots.

   ![App in Browser](<Screenshot 2025-04-14 170051.png>)
   
   _This is the successful deployment of the app in the browser using NodePort service._
---

## 🔗 Detailed Documentation

- [Pods Setup](./PODS/README.md)
- [ReplicaSet Setup](./REPLICASET/README.md)
- [Deployment Setup](./DEPLOYMENTS/README.md)

---

## 💡 Conclusion

This project demonstrates the deployment of a **Hello World** application using Kubernetes and Minikube, leveraging Pods, ReplicaSets, and Deployments. The application is accessible via a browser through a NodePort service. 🚀

The modular structure of this project ensures flexibility for future scaling or modifications, allowing independent management of Pods, ReplicaSets, and Deployments without impacting the entire system.