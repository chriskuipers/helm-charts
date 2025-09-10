# helm-charts

This repository contains Helm charts for experimenting with Kubernetes deployments.

## test-app

A simple Hello World Helm chart that deploys an nginx container to show a basic webpage.

### Prerequisites

- Kubernetes cluster
- Helm installed

### Installation

1. Clone this repository.
2. Navigate to the test-app directory.
3. Run the following command to install the chart:

```bash
helm install test-app ./test-app
```

### Accessing the Application

After installation, the nginx service will be running. To access the webpage:

```bash
kubectl port-forward svc/test-app 8080:80
```

Then, open your browser and go to `http://localhost:8080` to see the nginx welcome page.

### Uninstall

To uninstall the chart:

```bash
helm uninstall test-app
```

## Using as a Helm Repository

This repository is set up as a Helm chart repository using GitHub Actions and Pages.

### Add the Repository

```bash
helm repo add helm-charts https://chriskuipers.github.io/helm-charts/
helm repo update
```

### Install Charts

```bash
helm install my-test-app helm-charts/test-app
```

### List Available Charts

```bash
helm search repo helm-charts
```

### Remove the Repository

```bash
helm repo remove helm-charts
```

Note: Ensure GitHub Pages is enabled for the repository on the `gh-pages` branch.
