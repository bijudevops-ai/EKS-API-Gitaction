# Deploying Python API to EKS cluster in AWS using Github Actions

![image](https://github.com/user-attachments/assets/898607cb-b628-4410-b776-3bbf2e65588b)


In this session , I am creating a Flask CRUD application interacting with a single table called inventory kept in Postgres database .   

Pre-requisites- Docker Desktop, Minikube in Dev machine to test ,VS Code
Tools/Technologies- Python, Flask API, Docker Hub, MiniKube, AWS EKS, Argo CD, Prometheus, Grafana,EKSCTL utility.


 docker build -t bijuthottathil/flask-postgres-microservice:latest .
 docker tag bijuthottathil/flask-postgres-microservice:latest 588268565787.dkr.ecr.us-east-1.amazonaws.com/flask-postgres-microservice:latest

 eksctl create cluster   --name flask-cluster   --region us-east-1   --nodegroup-name flask-nodes   --node-type t3.medium   --nodes 2   --managed

Note:- I am still updating Readme and Medium article. It will be ready in 2 days







