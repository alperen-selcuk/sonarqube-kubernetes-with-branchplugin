# SonarQube with Community Branch Plugin

SonarQube deployment on Kubernetes with Community Branch Plugin for multi-branch analysis.

## Versions

- SonarQube: 25.4.0-community
- Community Branch Plugin: 25.4.0
- PostgreSQL: enabled

## Installation

Add SonarQube Helm repository:
```bash
helm repo add sonarqube https://SonarSource.github.io/helm-chart-sonarqube
helm repo update
```

Create namespace:
```bash
kubectl create namespace sonarqube
```

Install SonarQube:
```bash
helm install sonarqube sonarqube/sonarqube \
  --namespace sonarqube \
  --values values.yaml
```

## Access

Port forward to access SonarQube:
```bash
kubectl port-forward service/sonarqube-sonarqube 9000:9000 -n sonarqube
```

Open browser: `http://localhost:9000`

Login: admin/admin (change password on first login)
