# 🧠 Helm Crash Course — Complete Practical Guide

Welcome to the **Helm Crash Course**!  
This repo contains all the practical examples used in the session — from installing charts to publishing your own public Helm chart using **GitHub Pages + Actions** 🚀

---

## 📘 What You'll Learn

In this crash course, we cover:

1. **Helm Basics**
   - Installing Helm  
   - Understanding charts, releases, and templates  
   - Using values.yaml for configuration

2. **Installing Public Charts**
   - Installing **Prometheus**, **Grafana**, and other Bitnami charts  
   - Exploring chart values and custom overrides  
   - Common Helm commands: `install`, `upgrade`, `rollback`, `uninstall`, `template`, `list`

3. **Creating Your Own Chart**
   - `helm create myapp`  
   - Adding custom templates (Deployment, Service, ConfigMap, etc.)  
   - Using `.Values` and parameterizing manifests

4. **Publishing Charts Publicly**
   - Packaging your chart (`.tgz`)  
   - Generating an `index.yaml`  
   - Hosting charts on **GitHub Pages**

5. **Automation with GitHub Actions**
   - Automatically packaging and publishing new chart versions  
   - Using [Chart Releaser Action](https://helm.sh/docs/howto/chart_releaser_action/)  
   - Continuous delivery for your Helm charts!

---

## 🧩 Repository Structure
```bash
helm_crash_course/
├── charts/
│   └── myapp/
│       ├── Chart.yaml          # Chart metadata
│       ├── values.yaml         # Default configuration
│       └── templates/          # Kubernetes manifests
│           ├── _helpers.tpl
│           ├── deployment.yaml
│           └── service.yaml
│
├── index.yaml                  # Helm repository index (auto-generated)
├── index.html                  # Optional landing page for GitHub Pages
└── README.md
```
---

## 🚀 Using This Repository

### Add This Repository as a Helm Repo
```bash
helm repo add keerthik https://iamkeerthik.github.io/helm_crash_course/
helm repo update

helm install myapp keerthik/myapp
```
Upgrade or Uninstall
```bash
helm repo update
helm search repo keerthik
helm upgrade myapp keerthik/myapp
helm uninstall myapp
```
🔄 Automation Workflow

Whenever you push a change to the main branch:
	1.	The GitHub Action runs automatically.
	2.	It packages your chart and updates index.yaml.
	3.	It publishes both to the main branch.
	4.	GitHub Pages serves the latest chart at:
👉 https://iamkeerthik.github.io/helm_crash_course/￼

### 🧩 Common Helm Commands

| Command | Description |
|----------|--------------|
| `helm create myapp` | Scaffold a new Helm chart named **myapp** |
| `helm template myapp/` | Render chart templates locally (no cluster needed) |
| `helm package myapp` | Package the chart into a `.tgz` archive |
| `helm repo index .` | Generate or update the `index.yaml` for your chart repository |
| `helm install myapp ./myapp` | Install the chart from your local directory |
| `helm upgrade myapp keerthik/myapp` | Upgrade an existing release using the published chart |
| `helm rollback myapp <rev>` | Roll back to a previous release revision |

