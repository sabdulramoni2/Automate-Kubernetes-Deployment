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

- Create terraform files on droplet server
  ![image](https://github.com/user-attachments/assets/060503c0-cf51-46c9-9ba4-16c8c8515071)

  ![image](https://github.com/user-attachments/assets/4f44d84a-9f41-4908-9daf-3b1f75b10915)



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
  
- Install the following dependencies on the host (which is ansible server in our case) that executes this module.
  
  ```
    python >=3.6
    kubernetes >=12.0.0
    PYYAML >=3.11
    jsonpatch
  ```

- Use the following command to check

  ```
      python3 -c "import YAML"
      python3 -c "import kubernetes"
      python3 -c "import jsonpatch"
  ```

  ![image](https://github.com/user-attachments/assets/83ec64ad-52de-4858-aada-beb5a6a2bcc2)


- Steps to resolve:
1.	Ensure you are in your project directory: cd ~/my_k8s_project
2.	Activate your virtual environment:
   ```
      source venv/bin/activate
   ```
3. After this command, your prompt must change. It should look something like this:
   ```
    (venv) root@ubuntu-s-2vcpu-2gb-nyc1-01:~/my_k8s_project#
   ```
    The (venv) prefix is the crucial indicator that you are now operating within the virtual environment.
   
4. In your Ansible Inventory (Recommended for a specific host/group). Add this two line
   ```
       localhost ansible_connection=local ansible_python_interpreter=/root/my_k8s_project/venv/bin/python
   ```
       
    ![image](https://github.com/user-attachments/assets/df7e1db7-c82f-4b1c-9ecd-9c9d77902649)





 
