# Dify AWS Terraform Deployment

This Terraform configuration deploys Dify on AWS using the following services:
- ECS Fargate for container orchestration
- RDS PostgreSQL for database
- ElastiCache for Redis
- S3 for storage
- Application Load Balancer for traffic distribution

## Prerequisites
- AWS CLI configured
- Terraform installed
- Valid AWS credentials

## Usage
1. Initialize Terraform:
```bash
terraform init
```

2. Review the planned changes:
```bash
terraform plan
```

3. Apply the configuration:
```bash
terraform apply
```

## Architecture
- Frontend: Application Load Balancer → ECS Fargate
- Backend Services:
  - API Service: ECS Fargate
  - Web Service: ECS Fargate
  - Worker Service: ECS Fargate
  - Sandbox Service: ECS Fargate
- Databases:
  - Main DB: RDS PostgreSQL
  - Vector DB: RDS PostgreSQL (pgvector)
  - Cache: ElastiCache Redis 