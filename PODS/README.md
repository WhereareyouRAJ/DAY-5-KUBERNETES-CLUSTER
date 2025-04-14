# 🐳 Pod Deployment - Hello World App

This README provides a step-by-step guide to deploying a single Pod and exposing it using a NodePort service in a Minikube cluster.

---

## 📁 Files in This Folder

- **`pod.yaml`** – Defines the Pod configuration to run a Hello World Docker container.
- **`service.yaml`** – Configures a NodePort Service to expose the Pod externally.
- **`README.md`** – This documentation file.

---

## 🎯 Objective

Deploy a simple Pod and verify its accessibility via a browser using Kubernetes and Minikube.

---

## 🚀 Deployment Steps

### 1️⃣ Apply the Pod and Service Configuration

Run the following commands to deploy the Pod and Service:

```bash
kubectl apply -f pod.yaml
kubectl apply -f service.yaml
```

### 2️⃣ Verify Deployment and Retrieve Access URL

Check the status of the Pod and Service:

```bash
kubectl get pods
kubectl get svc
```

Retrieve the external URL for the service:

```bash
minikube service my-service --url
```

### 3️⃣ Access the Application in a Browser

1. Copy the URL returned by the `minikube service` command.
2. Paste the URL into your browser to verify the application is running.

---

## 🖼️ Screenshots

1. **Pod, Service, and URL Output**  
    ![Pod and Service Output](<Screenshot 2025-04-14 120401.png>)

2. **Application in Browser**  
    ![Working Application](<Screenshot 2025-04-14 142700.png>)

---

## 🧠 Key Notes

- Ensure the Docker image’s internal port matches the `containerPort` in `pod.yaml`.
- The `targetPort` in `service.yaml` must align with the `containerPort`.
- Use the `NodePort` service type to expose the application to your host machine.
- The command `minikube service <service-name> --url` provides the correct external URL.
- If using Minikube with Docker, keep the terminal session active while running the service.

---

## 📌 Example Configuration

- **Docker Image**: `karthequian/helloworld`
- **App Port Inside Container**: `80`
- **Pod `containerPort`**: `80`
- **Service `targetPort`**: `80`
- **Service `nodePort`**: `30080` (for external access)

---

## ✅ Result

The Hello World application was successfully deployed and is accessible via a browser. 🎉