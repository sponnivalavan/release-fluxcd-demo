# FluxCD Demo Repository

This repository demonstrates the usage of FluxCD for GitOps-based Kubernetes deployments. It contains sample applications and configurations that showcase FluxCD's capabilities.

## Repository Structure

```
.
├── apps/                    # Application manifests
│   └── base/               # Base configurations
│       └── podinfo/        # Podinfo application
├── clusters/               # Cluster-specific configurations
│   └── dev/               # Development cluster
└── flux-system/           # FluxCD system configurations
```

## Prerequisites

- Kubernetes cluster
- `flux` CLI installed
- `kubectl` configured to access your cluster

## Getting Started

1. Clone this repository:
   ```bash
   git clone <your-repo-url>
   cd <repo-name>
   ```

2. Bootstrap FluxCD in your cluster:
   ```bash
   flux bootstrap github \
     --owner=<your-github-username> \
     --repository=<your-repo-name> \
     --branch=main \
     --path=clusters/dev \
     --personal
   ```

3. Verify the installation:
   ```bash
   flux get all
   ```

## Applications

### Podinfo
A simple demo application that shows various Kubernetes features. It's deployed in the `podinfo` namespace.

## Contributing

Feel free to submit issues and enhancement requests!
