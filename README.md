# Darey.io DevOps Environment Setup

## System
- OS: macOS
- Shell: zsh
- Architecture: Apple Silicon / arm64

## Package Manager
Homebrew was used as the primary package manager for CLI tools.

Node.js is managed with NVM so different Node.js versions can be managed without duplicate installations.

## Tools Verified
- Git
- Docker
- kubectl
- Minikube
- Helm
- Terraform
- Ansible
- AWS CLI
- Azure CLI
- Node.js
- npm
- jq

## Kubernetes Setup
Minikube is used as the local Kubernetes cluster.

kubectl is configured to use the minikube context.

The Minikube control plane, kubelet, and API server are running, and the Kubernetes node reports a Ready status.

Helm is installed for Kubernetes package management.

## Troubleshooting and Installation Logic
Before installing any tool, I checked whether it was already installed using commands such as:

command -v <tool>

and:

brew list --versions <tool>

This prevented duplicate installations.

Terraform was already installed but outdated, so it was upgraded through the existing Homebrew installation.

AWS CLI is installed correctly, but AWS authentication is currently unavailable because the AWS account is disabled due to a billing issue.

## Environment Configuration
The zsh configuration file is:

~/.zshrc

It configures NVM and adds Homebrew binaries to the PATH.
