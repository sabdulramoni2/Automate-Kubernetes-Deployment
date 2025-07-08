# **Automate Kubernetes Deployment**

## **Project Overview**
This project demonstrates the provisoning of EKS cluster using terraform and confguredAnsible to connect to the cluster. Then deployed Deployment and Service components on the cluster.

---
  
## **Feature**

### **EKS provisioning using Terraform**

- Install ansible on digital oceaan server.
- install terraform on digital ocean server.
- Created K8s cluster on AWS with terraform.
- Configure ansible to connect to EKS.
- Deployed Deployment and Service components on the cluster.
- Terraform destroy (IMPORTANT: delete all your components, if you don’t want to get charged for a running cluster!)


### **Diagrammatic Presentation**
- Install ansible on digital oceaan server.
  ![image](https://github.com/user-attachments/assets/10ea02e0-d399-4ac0-8ea5-aebc766b01cf)
- Connect to server via ssh
  ![image](https://github.com/user-attachments/assets/16aa9534-9bd4-4619-9d86-6fac0a7166f2)
- Ran the following command to install ansible
  ```
  apt update
  apt install ansible-core
  apt install python3-boto3
  ```
  ![image](https://github.com/user-attachments/assets/79a7427a-8222-4d5a-acb1-24e2cad5143d)

  ![image](https://github.com/user-attachments/assets/1d37ea01-8df6-4259-a6d6-44b088bc53ea)


- install terraform on digital ocean server.
- Ran the following command to install terraform
  ```wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
     echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee                                        /etc/apt/sources.list.d/hashicorp.list
     sudo apt update && sudo apt install terraform
  ```

  ![image](https://github.com/user-attachments/assets/2ae5abd9-731d-4b25-ad73-3e44b8dc583c)

- Created K8s cluster on AWS with terraform.
  
  ![image](https://github.com/user-attachments/assets/f584ca33-8475-42d6-a132-bdce55976bb7)

  ![image](https://github.com/user-attachments/assets/6b406d5f-cceb-482a-98b1-75cb71346d76)


  ![image](https://github.com/user-attachments/assets/03f071e8-f948-4cf5-92aa-cc725e36c9c8)

- Configure ansible to connect to EKS.

    - Use this command to generate kubeconfig file that will be provided to ansible to connect to the cluster.
     ```
          aws eks update-kubeconfig --region us-east-2 --name myapp-eks-cluster --kubeconfig /root/kubeconfig_myapp-eks-cluster
     ````
    
    ![image](https://github.com/user-attachments/assets/f9b7ce6b-0450-4a12-9a52-f69de7374075)



 
