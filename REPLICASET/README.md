# ⚙️ ReplicaSet Deployment - Hello World App

This README provides a step-by-step guide to deploying multiple replicas of a Pod using a ReplicaSet and exposing them via a NodePort service in a Minikube Kubernetes cluster.

---

## 📁 Files in This Folder

- **`replicaset.yaml`** – Defines a ReplicaSet to manage multiple Pods (replicas).
- **`service.yaml`** – Configures a NodePort service to expose the ReplicaSet.
- **`README.md`** – Documentation (this file).

---

## 🎯 Objective

Demonstrate the deployment of multiple replicas of an application and verify accessibility through a single service endpoint.

---

## 🚀 Deployment Steps

### 1️⃣ Apply the ReplicaSet and Service Configuration

Run the following commands to deploy the ReplicaSet and Service:

```bash
kubectl apply -f replicaset.yaml
kubectl apply -f service.yaml
```

### 2️⃣ Verify Deployment

Check the status of the ReplicaSet, Pods, and Service:

```bash
kubectl get replicaset
kubectl get pods
kubectl get svc
minikube service my-service --url
```

### 3️⃣ Access the Application

- Copy the URL from the `minikube service` output.
- Open the URL in your browser to confirm the app is served by one of the replicated Pods.

---

## 🖼️ Screenshots

### Screenshot 1: ReplicaSet, Pods, Service, and URL Output
![ReplicaSet, Pods, Service & URL Output](<Screenshot 2025-04-14 164243.png>)

### Screenshot 2: Browser Displaying Hello World App
![Hello World App Running](<Screenshot 2025-04-14 164318.png>)

---

## 🧠 Key Notes

- The **ReplicaSet** ensures the specified number of Pods are always running. If a Pod fails, it is automatically recreated.
- The **selector** in the ReplicaSet must match the labels of the Pods it manages.
- The **Service** uses the same selector to route traffic to the Pods.
- **NodePort** enables external access to the service from your local machine.
- If using the Docker driver on Minikube (Windows), keep the terminal running while accessing the app.

---

## 📌 Configuration Details

- **Replicas**: 3
- **Container Image**: `karthequian/helloworld`
- **App Port Inside Container**: 80
- **ReplicaSet `containerPort`**: 80
- **Service `targetPort`**: 80
- **Service `nodePort`**: 30080 (for external access)

---

## ✅ Outcome

- ReplicaSet successfully created.
- Application accessible via browser.
- Traffic distributed across replicated Pods.

--- 

Happy Kubernetes-ing! 🚀