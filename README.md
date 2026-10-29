# 🚀 AWS Serverless Static Website (NexusCloud Solutions)

A production-grade, secure, and globally-distributed static website hosted entirely on AWS serverless infrastructure. This project demonstrates foundational cloud engineering concepts including secure storage, content delivery network (CDN) caching, SSL/TLS encryption, and global routing.

---

## 🏗️ Architecture & Data Flow

```text
[ User ] 
   │
   ▼
[ Route 53 ] (DNS Custom Domain Routing - Optional)
   │
   ▼
[ CloudFront CDN ] (Global Edge Caching & HTTPS Termination)
   │
   ▼ (Origin Access Control - OAC)
[ Amazon S3 Bucket ] (Private Static Origin Storage)

---

## 🛠️ Implementation Approaches

This project has been implemented using two different approaches to master both manual AWS management and modern Infrastructure as Code (IaC):

### 1. Manual Approach (AWS Console)
* **S3 Bucket Configuration:** Created a private S3 bucket and ensured Public Access Block is enabled for security.
* **CloudFront OAC:** Set up Origin Access Control (OAC) to block direct S3 access and route traffic exclusively through CloudFront.
* **Bucket Policy:** Configured an S3 bucket policy allowing only the authorized CloudFront distribution to fetch objects.

### 2. Infrastructure as Code (IaC) via Terraform
* Automated the entire infrastructure deployment using declarative configuration (`main.tf`).
* **Core Commands Used:**
  - `terraform init` (To initialize provider plugins)
  - `terraform apply` (To provision resources automatically)
  - `terraform destroy` (To safely clean up resources when no longer needed)

### 📁 Project Structure
- `main.tf` -> Terraform configuration file containing the AWS Provider, S3 bucket, OAC, CloudFront distribution, and bucket policy.
- `index.html`, `about.html`, etc. -> Static website portfolio files.
