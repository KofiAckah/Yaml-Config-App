# YAML Configuration App 🚀

A comprehensive YAML-based application configuration management system designed for cloud-native deployments. This project demonstrates best practices in configuration management, security, and Kubernetes orchestration.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Configuration Details](#configuration-details)
- [Validation Tools](#validation-tools)
- [Getting Started](#getting-started)
- [Usage Examples](#usage-examples)
- [Screenshots](#screenshots)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project provides a production-ready YAML configuration setup for modern cloud applications. It includes:

- Application settings and metadata
- Database connection configurations
- Feature flags for dynamic functionality
- Cache and API rate limiting settings
- Kubernetes deployment manifests
- Secret management for sensitive data

## ✨ Features

- **Modular Configuration**: Separate concerns with ConfigMaps and Secrets
- **Security First**: Proper secret management and encrypted credentials
- **Cloud-Native**: Ready for Kubernetes deployment
- **Scalable**: Support for horizontal pod autoscaling (3 replicas)
- **Health Monitoring**: Built-in liveness and readiness probes
- **Resource Management**: CPU and memory limits configured
- **Validated**: All configurations tested with industry-standard validators

## 📁 Project Structure

```
YAML Config App/
├── app-config.yaml          # Main configuration file
├── README.md                # Project documentation
├── Assets/                  # Validation screenshots
│   ├── yaml-validator.png
│   ├── yaml-to-json.png
│   └── json-validator.png
```

## ⚙️ Configuration Details

### Application Settings
```yaml
application:
  name: MyApplication
  version: 1.0.0
  environment: production
  log_level: INFO
```

### Server Configuration
```yaml
server:
  host: 0.0.0.0
  port: 8080
```

### Database Configuration
```yaml
database:
  engine: postgresql
  host: postgres-service
  port: 5432
  name: myapp_db
  username: Livingstone
  password: secure_password_1234
```

### Feature Flags
```yaml
features:
  enable_auth: true
  enable_cache: true
  enable_metrics: true
```

### Cache Settings
```yaml
cache:
  ttl: 3600
  max_size: 1000
```

### API Configuration
```yaml
api:
  timeout: 30
  max_retries: 3
  rate_limit: 100
```

## 🔍 Validation Tools

This project has been validated using industry-standard tools to ensure configuration integrity:

### 1. YAML Validator
**Tool**: [YAML Lint](https://www.yamllint.com/)

Validates YAML syntax and structure to ensure proper formatting and prevent parsing errors.

![YAML Validator](./Assets/yaml-validator.png)

### 2. YAML to JSON Converter
**Tool**: [Online YAML Tools](https://onlineyamltools.com/convert-yaml-to-json)

Converts YAML configurations to JSON format for compatibility and data interchange.

![YAML to JSON](./Assets/yaml-to-json.png)

### 3. JSON Validator
**Tool**: [JSON Lint](https://jsonlint.com/)

Validates the converted JSON to ensure data integrity during format conversion.

![JSON Validator](./Assets/json-validator.png)

## 🚀 Getting Started

### Prerequisites

- Kubernetes cluster (minikube, kind, or cloud provider)
- kubectl CLI tool
- Docker (for containerization)
- Text editor (VS Code recommended)

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd "YAML Config App"
```

2. Validate your YAML configuration:
```bash
# Using yamllint
yamllint app-config.yaml

# Or validate online at https://www.yamllint.com/
```

3. Apply the configuration to your Kubernetes cluster:
```bash
kubectl apply -f app-config.yaml
```

4. Verify the deployment:
```bash
kubectl get pods
kubectl get services
kubectl get configmaps
kubectl get secrets
```

## 💻 Usage Examples

### View ConfigMap
```bash
kubectl describe configmap app-config
```

### View Secrets (base64 encoded)
```bash
kubectl get secret app-secrets -o yaml
```

### Check Pod Logs
```bash
kubectl logs -f deployment/myapp-deployment
```

### Port Forwarding for Local Testing
```bash
kubectl port-forward service/myapp-service 8080:80
```

### Scale Deployment
```bash
kubectl scale deployment myapp-deployment --replicas=5
```

### Update Configuration
```bash
# Edit the app-config.yaml file
kubectl apply -f app-config.yaml

# Restart pods to pick up changes
kubectl rollout restart deployment myapp-deployment
```

## 📸 Screenshots

### YAML Validation Results
All configurations have been validated for syntax correctness and best practices.

**YAML Lint Validation**
![YAML Validation](./Assets/yaml-validator.png)

**YAML to JSON Conversion**
![YAML to JSON](./Assets/yaml-to-json.png)

**JSON Validation**
![JSON Validation](./Assets/json-validator.png)

## 🛡️ Best Practices

1. **Never commit secrets to version control**
   - Use `.gitignore` for sensitive files
   - Utilize Kubernetes Secrets or external secret management (Vault)

2. **Validate before deployment**
   - Always validate YAML syntax
   - Test configurations in development first

3. **Use namespaces**
   - Separate environments (dev, staging, prod)
   - Implement RBAC for access control

4. **Resource limits**
   - Define CPU and memory requests/limits
   - Prevent resource exhaustion

5. **Health checks**
   - Implement liveness and readiness probes
   - Enable automatic pod recovery

6. **Version control**
   - Tag releases with semantic versioning
   - Document configuration changes

## 🧪 Testing

### Validate YAML Locally
```bash
# Install yamllint
pip install yamllint

# Run validation
yamllint app-config.yaml
```

### Test Kubernetes Deployment
```bash
# Dry run to check for errors
kubectl apply -f app-config.yaml --dry-run=client

# Apply to test namespace
kubectl apply -f app-config.yaml -n test
```

## 🔗 Useful Links

- [YAML Validator](https://www.yamllint.com/) - Validate YAML syntax
- [YAML to JSON Converter](https://onlineyamltools.com/convert-yaml-to-json) - Convert formats
- [JSON Validator](https://jsonlint.com/) - Validate JSON structure
- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [YAML Specification](https://yaml.org/spec/)

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Livingstone Kofi Ackah**

- GitHub: [@KofiAckah](https://github.com/KofiAckah)

## 🙏 Acknowledgments

- Validation tools by YAML Lint, Online YAML Tools, and JSON Lint
- Kubernetes community for excellent documentation
