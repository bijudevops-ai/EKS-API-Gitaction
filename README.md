# EKS-API-K8S
1. ![image](https://github.com/user-attachments/assets/0d812d65-be46-40b7-aa33-aa698fe0ba73)
![image](https://github.com/user-attachments/assets/eb820c97-fa9c-47bb-967c-7e59dc5261ad)

2. PS D:\Projects\Kubernetes\EKS-API-K8S> aws ecr create-repository --repository-name flask-api
3. PS D:\Projects\Kubernetes\EKS-API-K8S> aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 588268565787.dkr.ecr.us-east-1.amazonaws.com
Login Succeeded

4. docker build -t bijuthottathil/flask-postgres-microservice:latest .
5. docker tag bijuthottathil/flask-postgres-microservice:latest 588268565787.dkr.ecr.us-east-1.amazonaws.com/flask-postgres-microservice:latest
6. ![image](https://github.com/user-attachments/assets/7c02ca8f-af1c-4cb1-908d-b3a2ba0634f3) ![image](https://github.com/user-attachments/assets/cd84dcc8-4b37-4b00-8910-ecac42432991)
7. eksctl create cluster   --name flask-cluster   --region us-east-1   --nodegroup-name flask-nodes   --node-type t3.medium   --nodes 2   --managed

8. Cluster is created ![image](https://github.com/user-attachments/assets/da005a56-f6c0-425b-9232-155ee25e37b6)
9. PS D:\Projects\Kubernetes\EKS-API-K8S> aws eks update-kubeconfig --region us-east-1 --name flask-cluster
>> kubectl get nodes
Added new context arn:aws:eks:us-east-1:588268565787:cluster/flask-cluster to C:\Users\bijum\.kube\config
No resources found
10. ![image](https://github.com/user-attachments/assets/9cdd39af-b517-452b-b69c-9a829c71593e)

11 ![image](https://github.com/user-attachments/assets/1cbc52ec-bc03-4dd9-99fd-801aa6e65795)

12. yaml file
13. ![image](https://github.com/user-attachments/assets/d728feeb-a569-4772-b204-de0fbe9b8a9a)
14. Run Gitactions ![image](https://github.com/user-attachments/assets/989c6fb5-a05d-44ce-89e0-b69cb3c84e96)




