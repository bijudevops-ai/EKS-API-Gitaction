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


 ![image](https://github.com/user-attachments/assets/b2a11ae4-2805-4edd-bd5e-997409525906)

 Execute Gitaction file available in the github   
 ![image](https://github.com/user-attachments/assets/00ec73d3-a613-4fdc-89fa-d9af802df9a3)

  Once GithubAction file is executed, you will see log like below  
  
![image](https://github.com/user-attachments/assets/5890d6ce-2d05-444f-a578-88a1e4d8bb87)  
![image](https://github.com/user-attachments/assets/381adbe5-5940-4daf-bf5e-12229c93a75d)  

![image](https://github.com/user-attachments/assets/c2fda38b-50cb-4531-8198-e9d6722f9fd8)  

Connected to postgres DB using loadbalancer url in PgAdmin using the AWS loadbalancer set for postgres DB  
![image](https://github.com/user-attachments/assets/a38304d5-0acc-4776-aae7-96eede5a023e)    

Executed DB Scripts to create new table Inventory and few records  
![image](https://github.com/user-attachments/assets/a2b11fa4-576d-4606-b45b-a6c5a280ec4f)


Checked health the microservice   
![image](https://github.com/user-attachments/assets/7fcb3715-fa4b-4e99-a60a-146322985e65)

Accessed UI for communicating with Service . It part of my application ..

![image](https://github.com/user-attachments/assets/406af3d3-d46a-4c14-ada8-3c1a45df9d29)  

![image](https://github.com/user-attachments/assets/b1b94747-15bd-4134-bf01-f4ad820c5200)  

![image](https://github.com/user-attachments/assets/acbf4fbe-b5e6-480d-b2be-149814bee385)  


![image](https://github.com/user-attachments/assets/59bfc156-d667-4f7c-92f9-8ba14780a92d)  


![image](https://github.com/user-attachments/assets/3302799f-e705-4f4a-ae44-a0e930eda134)


















