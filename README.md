# Argo CD Configuration Demo

This project demonstrates the **power and simplicity of GitOps using Argo CD** by managing Kubernetes application deployment configurations through declarative YAML files.

## 🔥 Project: `argocd-configuration`

GitHub Repository: [argo-project-configuration](https://github.com/benalif/argo-project-configuration/tree/main)

### 🎯 Purpose

This project serves as a live **example of GitOps principles** using [Argo CD](https://argo-cd.readthedocs.io/). It is designed to showcase how applications can be:

- Automatically deployed to a Kubernetes cluster
- Continuously synchronized with changes pushed to Git
- Managed declaratively using YAML manifests

---

## 🚀 Getting Started with Argo CD

### 📦 1. Install Argo CD

Install Argo CD on your Kubernetes cluster using the official documentation:

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
### 🔗 2. Access Argo CD UI
Use kubectl port-forwarding to securely access the Argo CD API server:
```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
Then access Argo CD at:
```
https://localhost:8080
```

### 🔑 3. Login Using the CLI
Generate a random password for the admin user:
```
argocd admin initial-password -n argocd
```
<img width="1718" alt="Screenshot 2025-06-28 at 6 19 03 PM" src="https://github.com/user-attachments/assets/32a5a1df-81f8-49b8-add4-62d73579e346" />

### 4. Deploy Your Application
Clone this configuration repository:
```
git clone https://github.com/benalif/argo-project-configuration.git
cd argo-project-configuration
```
Apply the Argo CD Application resource:
```
kubectl apply -f application.yaml
```
<img width="1718" alt="Screenshot 2025-06-28 at 6 02 59 PM" src="https://github.com/user-attachments/assets/49d28dd7-077a-4202-8b8b-d11dec99c19a" />

### 💡 Benefits of Using Argo CD
Full automation of Kubernetes deployments using Git as the source of truth.

- Improved visibility and auditability with a web UI that shows real-time app status and history.

- Rapid rollbacks by reverting Git commits, with no manual cluster changes.

- Drift detection to ensure the cluster matches the declared state.

- Environment isolation through structured overlays for dev, staging, and production.

- Developer-friendly workflow — just push to Git, and Argo CD handles the rest.
