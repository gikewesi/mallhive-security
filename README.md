# 🔐 MallHive Security

This repository contains security configurations, policies, and infrastructure for the **MallHive cloud-native e-commerce platform**. It ensures secure communication, access control, and protection of sensitive data across the platform's services.

---

## 📄 What This Repo Covers

- Secure storage of credentials using **AWS Secrets Manager**
- Data encryption via **AWS Key Management Service (KMS)**
- IAM role-based access control for all services
- Kubernetes-level RBAC enforcement
- Network policies for intra-cluster isolation
- Mutual TLS (mTLS) for internal service communication

---

## 🔑 Components

### 1. **Secrets Management**
- Use AWS Secrets Manager to securely store and rotate secrets such as:
  - DB credentials
  - API keys
  - Third-party tokens
- Terraform configuration included for provisioning and permissions.

### 2. **Encryption**
- Encrypt sensitive data at rest and in transit using AWS KMS.
- Integrate KMS with:
  - PostgreSQL (via RDS encryption)
  - S3 buckets (product assets, reports)
  - Secrets Manager

### 3. **IAM Policies & Roles**
- Define least-privilege IAM roles for:
  - Application services
  - CI/CD pipelines
  - Admin users
- Inline and managed policies configured through Terraform.

### 4. **Kubernetes Security**
- Enforce Kubernetes RBAC to limit access by namespace and role.
- Use Kubernetes `NetworkPolicy` to control traffic between pods.
- Mutual TLS (mTLS) setup for internal gRPC communication (where applicable).

---

## ⚙️ Tools Used

- **Terraform** – Infrastructure as Code for managing IAM, Secrets, KMS
- **kubectl / Helm** – Applying RBAC, NetworkPolicies
- **AWS CLI** – Managing security services
- **OPA/Gatekeeper (optional)** – Enforce security policies on Kubernetes resources

---

## 📌 Future Improvements

- Automate IAM Role and Policy linting
- Integrate [AWS Security Hub](https://aws.amazon.com/security-hub/) for real-time security monitoring
- Audit logging and compliance checks with tools like **CloudTrail** and **Config Rules**

---

## 🧾 License

MIT – feel free to use and adapt with attribution.
