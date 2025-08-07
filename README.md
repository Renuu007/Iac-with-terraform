# 🚀 IaC with Terraform: Docker Nginx Container

## 📦 Overview

This project uses [Terraform](https://www.terraform.io/) to provision a Docker container running the latest [nginx](https://nginx.org/) image.  
It leverages the [kreuzwerker/docker](https://registry.terraform.io/providers/kreuzwerker/docker/latest) provider for Docker integration.

## 🛠️ Prerequisites

- Ubuntu 24.04.2 LTS (dev container)
- Docker installed and running
- Terraform installed (`sudo apt install terraform`)
- Access to `/var/run/docker.sock`

## 📁 Files

- `main.tf` — Terraform configuration for nginx Docker container.

## ▶️ Usage

1. **Initialize Terraform**
   ```bash
   terraform init
   ```

2. **Review the execution plan**
   ```bash
   terraform plan
   ```

3. **Apply the configuration**
   ```bash
   terraform apply
   ```
   Type `yes` when prompted.

4. **Verify the container is running**
   ```bash
   docker ps
   ```
   You should see `nginx_container` with port `8080` mapped to `80`.

5. **Open nginx in your browser**
   ```bash
   $BROWSER http://localhost:8080
   ```

## 📝 main.tf Explained

- **Provider Block:** Uses `kreuzwerker/docker` to connect to Docker.
- **docker_image Resource:** Pulls the latest nginx image.
- **docker_container Resource:** Runs `nginx_container` from the nginx image, mapping port 8080 on the host to port 80 in the container.

## 🧹 Clean Up

To remove all resources created by Terraform:
```bash
terraform destroy
```

---


🌟 Happy Automating! 🌟