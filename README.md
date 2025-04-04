# Deployment Workflow Steps (README.md)

## 1. Repository Checkout

The actions/checkout@v2 GitHub Action is used to clone the repository into the runner environment.

## 2. SSH Deployment Configuration

Environment variables are set using repository secrets, including:

- SSH keys
- SSH username
- Remote host address
- Project path on the remote server

Then:

- The .ssh directory is created in the runner environment.
- The SSH private key is configured for authentication.
- The remote host is added to the known hosts using ssh-keyscan.

## 3. SSH Connection and Remote Deployment

An SSH connection is established with the remote server.

- If the project directory does not exist, the repository is cloned from GitHub to the specified path on the server.
- If the directory exists, the repository is pulled to update the code with the latest changes.

This process allows automated deployment to the remote environment using GitHub Actions and secure SSH access.
