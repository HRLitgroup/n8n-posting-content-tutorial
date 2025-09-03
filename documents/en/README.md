# Project: Automate Posting Content

## Introduction
The Automate Posting Content project was developed to streamline the process of publishing content across multiple channels of communication. Instead of manual posting, the system utilizes n8n – an open-source workflow automation platform – to automate the simultaneous publication of multiple posts on platforms such as Facebook, LinkedIn, and company websites.

## Prerequisites for setting up the project
1. A computer with sufficient RAM capacity
2. Basic knowledge of the technologies used:
- **N8N**: n8n (pronounced n-eight-n) is an open-source automation tool that helps us connect various apps and services to create workflows, much like a digital assembly line. It allows users to visually design these workflows with nodes, each representing a different step in the process. With n8n, we can automate tasks, manage data flow, and even integrate APIs, all without needing extensive programming skills.
  + For more information: [N8N Doc](https://docs.n8n.io/)
- **Docker**: [Docker Doc](https://docs.docker.com/get-started/docker-overview/)
- **VSCode**
- **Credentials and Access Token**
## Setup Guide

### 1. [Setup](./01-setup/)

- [Install Docker Desktop](./01-setup/01-docker-desktop.md)

### 2. [Development Environment](./02-vscode/)

- [Install VSCode](./02-vscode/01-install-vscode.md)

### 3. [N8N Setup](./03-n8n-setup/)

- [Clone and Set up N8N](./03-n8n-setup/01-clone-setup-n8n.md) - Complete setup including account creation and activation

### 4. [Authentication](./04-authentication/)

- [Get Access Token](./04-authentication/get-access-token.md)

### 5. [Workflows](./05-workflows/)

- [Create N8N Workflow](./05-workflows/01-create-n8n-workflow.md)

## 🚀 Quick Start

1. **Install Prerequisites**

   - [Install Docker Desktop](./01-setup/01-docker-desktop.md)
   - [Install VSCode](./02-vscode/01-install-vscode.md)

2. **Set up N8N**

   - [Clone and Set up N8N](./03-n8n-setup/01-clone-setup-n8n.md)

3. **Configure Authentication**

   - [Get Access Token](./04-authentication/get-access-token.md)

4. **Create Workflows**
   - [Create N8N Workflow](./05-workflows/01-create-n8n-workflow.md)

## 📁 Project Structure

```
n8n_auto_flow/
├── assets/                    # Images and static assets
├── documents/                 # This documentation
│   ├── en/                  # English documentation
│   ├── vi/                  # Vietnamese documentation
│   └── README.md            # Language selector
├── docker-compose.yml        # Docker configuration
└── README.md                 # Main project README
```

## 🔧 Prerequisites

- Docker Desktop
- VSCode (recommended)
- Git (optional)

## 📖 Additional Resources

- [N8N Official Documentation](https://docs.n8n.io/)
- [Docker Documentation](https://docs.docker.com/)
- [VSCode Documentation](https://code.visualstudio.com/docs)

## 🤝 Contributing

This documentation is part of the N8N Auto Flow project. Feel free to contribute by improving the documentation or adding new sections.
