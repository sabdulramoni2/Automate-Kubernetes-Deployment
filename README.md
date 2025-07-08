# **Automate Kubernetes Deployment**

## **Project Overview**
This project demonstrates the provisoning of EKS cluster using terraform and confguredAnsible to connect to the cluster. Then deployed Deployment and Service components on the cluster.

---
  
## **Feature**

### **EKS provisioning using Terraform**

- Created the VPC by using the VPC module
- Created the EKS cluster and worker nodes by using the EKS module
- Configured Kubernetes provider to authenticate with K8s cluster
- Applied configurations
- Deployed nginx Application/Pod
- Terraform destroy (IMPORTANT: delete all your components, if you don’t want to get charged for a running cluster!)
