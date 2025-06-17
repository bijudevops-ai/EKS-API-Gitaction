# Deploying Python API to EKS cluster in AWS using Github Actions

![image](https://github.com/user-attachments/assets/898607cb-b628-4410-b776-3bbf2e65588b)


In this session , I am creating a Flask CRUD application interacting with a single table called inventory kept in Postgres database .   

Pre-requisites- Docker Desktop, Minikube in Dev machine to test ,VS Code
Tools/Technologies- Python, Flask API, Docker Hub, MiniKube, AWS EKS, Argo CD, Prometheus, Grafana,EKSCTL utility.


 docker build -t bijuthottathil/flask-postgres-microservice:latest .  
 ![image](https://github.com/user-attachments/assets/bba1075a-f453-4440-828f-c0d1032f7a95)  


 docker tag bijuthottathil/flask-postgres-microservice:latest 588268565787.dkr.ecr.us-east-1.amazonaws.com/flask-postgres-microservice:latest  
 ![image](https://github.com/user-attachments/assets/e4bd0342-d9f9-402d-aa81-f18b2aad6793)


 eksctl create cluster   --name flask-cluster   --region us-east-1   --nodegroup-name flask-nodes   --node-type t3.medium   --nodes 2   --managed

 ![image](https://github.com/user-attachments/assets/34150bde-3fdc-4847-aab7-b89f66be604c)









