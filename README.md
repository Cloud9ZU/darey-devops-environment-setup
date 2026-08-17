# Darey.io DevOps Environment Setup

This repository documents the setup and verification of my local DevOps development environment on macOS.

## System Information

- **Operating System:** macOS
- **Shell:** zsh
- **Architecture:** Apple Silicon / arm64
- **Primary Package Manager:** Homebrew
- **Node.js Version Manager:** NVM

## Tools Installed and Verified

The following tools were installed or verified as part of the environment setup:

- Git
- Visual Studio Code
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

Detailed CLI version output is available in:

`tooling-verification.txt`

## Environment Configuration

The shell configuration used for this environment is included in:

`.zshrc`

The configuration:

- Loads NVM
- Sets the NVM directory
- Loads NVM shell completion
- Adds Homebrew binaries to the PATH

## Package Management Strategy

Homebrew was used as the primary package manager for command-line tools.

Before installing a tool, I checked whether it already existed using commands such as:

```bash
command -v <tool>
brew list --versions <tool>
```

This approach prevented duplicate installations.

Node.js is managed separately using NVM so that Node.js versions can be changed without maintaining duplicate Homebrew installations.

## Kubernetes Local Cluster

Minikube is used as the local Kubernetes distribution.

kubectl is configured to use the `minikube` context.

Verification confirmed:

- Minikube host is running
- kubelet is running
- Kubernetes API server is running
- kubeconfig is configured
- Minikube node status is `Ready`
- Helm is available for Kubernetes package management

Local cluster evidence is available in:

`kubernetes-proof.png`

## Screenshot Evidence

Additional installation and configuration evidence is stored in the:

`screenshots/`

directory.

Current evidence includes:

- `screenshots/git-version.png` — Git installation and configuration
- `screenshots/vscode-proof.png` — Visual Studio Code verification
- `screenshots/github-account.png` — GitHub CLI authentication and repository connection
- `screenshots/aws-cli.png` — AWS CLI installation verification
- `screenshots/azure-cli.png` — Azure CLI installation verification
- `screenshots/azure-account.png` — Azure account setup verification

## Cloud CLI Configuration

### AWS

AWS CLI is installed and available locally.

The AWS account associated with the existing credentials currently has an account/billing restriction. Therefore, AWS authentication cannot currently be successfully validated.

The CLI installation itself was verified independently.

### Azure

Azure CLI is installed and verified.

An Azure account was also created and account setup evidence is included in the screenshots directory.

## Troubleshooting and Setup Logic

Several checks were performed before making changes to the system.

### Duplicate Installation Prevention

Existing executables were checked with:

```bash
command -v <tool>
```

Homebrew-managed installations were checked with:

```bash
brew list --versions <tool>
```

### Terraform Upgrade

Terraform was already installed but was outdated.

Instead of installing a second copy, the existing Homebrew-managed Terraform installation was upgraded.

### AWS Authentication

AWS CLI installation was confirmed successfully.

An authentication test returned an invalid-token error because the AWS account currently has an account/billing issue. The CLI was therefore left installed without creating duplicate credentials or reinstalling the package.

## Git and GitHub Workflow

This repository was created locally with Git and connected to GitHub using GitHub CLI.

Changes were added through separate, meaningful commits instead of placing all subsequent evidence into one commit.

Examples include:

- Git installation verification
- VS Code verification
- GitHub account verification
- AWS CLI verification
- Azure CLI verification
- Azure account verification

## Repository Structure

```text
darey-devops-environment-setup/
├── .zshrc
├── README.md
├── kubernetes-proof.png
├── tooling-verification.txt
└── screenshots/
    ├── aws-cli.png
    ├── azure-account.png
    ├── azure-cli.png
    ├── git-version.png
    ├── github-account.png
    └── vscode-proof.png
```

## Conclusion

The local DevOps environment is configured with the required development, cloud, infrastructure-as-code, container, and Kubernetes tooling.

Installation methods, configuration files, version verification, Kubernetes cluster evidence, and supporting screenshots are included in this repository for assessment.
