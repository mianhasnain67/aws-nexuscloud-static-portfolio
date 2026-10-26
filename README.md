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