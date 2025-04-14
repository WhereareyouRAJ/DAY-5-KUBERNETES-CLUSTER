# 🚀 Deployment - Hello World App

This README outlines the steps to deploy a **Hello World** application using a **Kubernetes Deployment** and expose it via a **NodePort service** within a Minikube cluster.

---

## 📁 Files in This Folder

- `deployment.yaml` – Defines a Deployment with multiple replicas and self-healing capabilities.
- `service.yaml` – Configures a NodePort service to expose the Deployment externally.
- `README.md` – The document you're reading now. 😉

---

## 🎯 Objective

Deploy a containerized application with Kubernetes, leveraging features like automatic rollouts and rollbacks, and make it accessible via a browser.

---

## 🚀 Deployment Steps

### 1️⃣ Apply the Deployment and Service Configuration

Run the following commands to create the Deployment and Service:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 2️⃣ Verify Deployment, Pods, and Service Status

Check the status of the Deployment, Pods, and Service:

```bash
kubectl get deployments
kubectl get pods
kubectl get svc
```

Retrieve the service URL using Minikube:

```bash
minikube service my-service --url
```

### 3️⃣ Access the Application in a Browser

Copy the URL from the Minikube output and paste it into your browser to verify the application is running.

---

## 🖼️ Screenshots

1. **Deployment, Pods, Service, and Service URL Output**  
    ![Deployment Output](<Screenshot 2025-04-14 170019.png>)

2. **Hello World App in Browser**  
    ![Hello World App](<Screenshot 2025-04-14 170051.png>)

---

## 📌 Key Points to Remember

- **Deployment**: Manages Pods and supports rolling updates and rollbacks.
- **Replicas**: Specifies the number of Pods to run.
- **Labels**: Ensure `template.metadata.labels` in the Deployment matches the selectors in both the Deployment and Service.
- **NodePort**: Exposes the service externally via `<minikube-ip>:<nodePort>`.
- Use `minikube service my-service --url` for a quick access link.
- Keep the Minikube terminal running if using the Docker driver on Windows.

---

## 🧠 Example Configuration

- **Image**: `karthequian/helloworld`
- **Replicas**: `3`
- **Container Port**: `80`
- **Service Port**: `80`
- **Target Port**: `80`
- **NodePort**: `30080`

---

## ✅ Outcome

The Deployment was successfully created, and the application is served by Pods behind a NodePort service. The app is accessible via a browser, and everything works seamlessly! 💥