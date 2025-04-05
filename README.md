# Deployment Workflow Steps

## 1. Repository Checkout

The actions/checkout@v2 GitHub Action is used to clone the repository into the runner environment.

## 2. SSH Deployment Configuration

Those environment variables are set using repository secrets in github, including:

PRIVATE_KEY
HOST_NAME
USER_NAME
PROJECT_PATH
GIT_REPO: 

after to execute the script happen that: 

- Was created .ssh directory in the runner environment.
- was configured SSH private key for authentication.


## 3. SSH Connection and Remote Deployment

An SSH connection is established with the remote server.
There are two posibilities :  find the directory or directory does not exist, then it is maked. 
finally the repository is pulled to update the code with the latest changes, only main branch.

This process allows automated deployment to the remote environment using GitHub Actions and secure SSH access.
