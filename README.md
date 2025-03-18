# FluxCD Demo Repository

This repository demonstrates the usage of FluxCD for GitOps-based Kubernetes deployments. It contains sample applications and configurations that showcase FluxCD's capabilities.

## Repository Structure

```
.
├── apps/                    # Application manifests
│   └── base/               # Base configurations
│       ├── podinfo/        # Podinfo application (Git source)
│       ├── capacitor/      # Capacitor application (OCI source)
│       └── nginx/          # Nginx application (Helm source)
├── clusters/               # Cluster-specific configurations
│   └── dev/               # Development cluster
└── flux-system/           # FluxCD system configurations
```

## Prerequisites

- Kubernetes cluster
- `flux` CLI installed
- `kubectl` configured to access your cluster

## Getting Started

1. Fork this repository on your profile

2. Export environment variables:

   ```
   export GITHUB_USER=
   export GITHUB_TOKEN=
   ```

3. Clone the forked repository:

   ```bash
   git clone https://github.com/${GITHUB_USER}/release-fluxcd-demo.git
   cd release-fluxcd-demo
   ```

4. Bootstrap FluxCD in your cluster:

   ```bash
   flux bootstrap github \
    --owner=${GITHUB_USER} \
    --repository=release-fluxcd-demo \
    --branch=main \
    --personal \
    --path=clusters/dev
   ```

5. Verify the installation:
   ```bash
   flux get all -A
   ```

## Applications

### Podinfo

A simple demo application that shows various Kubernetes features. It's deployed in the `podinfo` namespace using GitRepository source and Kustomize deployment.

### Capacitor

A demo application showcasing OCI (Open Container Initiative) OCIRepository integration. It's deployed in the `capacitor` namespace using OCIRepository and Kustomize deployment.

### Nginx

A web server application demonstrating Helm integration. It's deployed in the `nginx` using HelmRepository source and HelmRelease deployment.
