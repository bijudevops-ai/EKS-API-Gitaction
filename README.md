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

# Setting up Argo CD and Grafana  

![image](https://github.com/user-attachments/assets/33be9e16-e086-44f2-af7d-fd9ffb11a5ef)   “argo” has been added to your repositories


![image](https://github.com/user-attachments/assets/a3727d79-18b5-4ee3-bf28-d4e539da37fc)  “grafana” has been added to your repositories


![image](https://github.com/user-attachments/assets/1b2e8d2a-e7df-4957-a15f-c580d7035f24)   …Successfully got an update from the “argo” chart repository
…Successfully got an update from the “grafana” chart repository
Update Complete. ⎈Happy Helming!⎈   

![image](https://github.com/user-attachments/assets/3939f986-6332-4324-ba8a-56b2583156c3)  

![image](https://github.com/user-attachments/assets/ffefe659-b068-476a-a7df-9519cf08a4e0)  

![image](https://github.com/user-attachments/assets/a2ad045c-531f-4926-9d08-438405f70669)  


![image](https://github.com/user-attachments/assets/94a7f7a1-8a2d-4098-a9c6-f8651724abf7)  ![image](https://github.com/user-attachments/assets/7348e98e-d996-4357-9a1b-7dc3d98572bb)

![image](https://github.com/user-attachments/assets/748a2dc3-504b-4915-ba74-7972a5990860)  ![image](https://github.com/user-attachments/assets/dd743ba0-e1d7-433e-829c-2fecd6b0f070)  


![image](https://github.com/user-attachments/assets/d1b810fd-baa0-480a-8f5b-1388c3b46d56)  

Running Argo CD application yaml .. 

![image](https://github.com/user-attachments/assets/40fde9e5-509f-444e-81ea-ffc05891e4bf)  application.argoproj.io/flask-app created  
![image](https://github.com/user-attachments/assets/c549d8a9-dee6-4f5e-8a9b-4c95049016ea)  
![image](https://github.com/user-attachments/assets/97ced8c0-9b6a-45b5-af11-4c89cb2b5c69)  


![image](https://github.com/user-attachments/assets/c2c9eee5-f27b-411d-b67d-0c655002805b) 

# Install Grafana in monitoring Namespace
PS D:\Projects\Kubernetes\EKS-API-Gitaction> helm install grafana grafana/grafana -n monitoring   --set service.type=LoadBalancer   --set adminPassword='admin123'   --set datasources."datasources\.yaml".apiVersion=1   --set datasources."datasources\.yaml".datasources[0].name=Prometheus   --set datasources."datasources\.yaml".datasources[0].type=prometheus   --set datasources."datasources\.yaml".datasources[0].url=http://prometheus-server.monitoring.svc.cluster.local  

![image](https://github.com/user-attachments/assets/cf2d25e9-539e-4b50-94b8-0377c1b560a8)   ![image](https://github.com/user-attachments/assets/e3bc99c1-1b3f-4ff0-b5a3-e8cdd1f7f57d)

![image](https://github.com/user-attachments/assets/d5bc47d0-86dc-4509-a497-0e99e731a085)   

![image](https://github.com/user-attachments/assets/90ad9047-d9c1-4edc-b563-f9ee75070d2b)  
![image](https://github.com/user-attachments/assets/854b20a6-ce11-4dfa-8f23-a53937813575)  ![image](https://github.com/user-attachments/assets/c6c505ff-948f-4c10-ac54-41986cf421ac)  

Login with admin/admin12 ..

Grafana is running in EKS   


![image](https://github.com/user-attachments/assets/a018f0dc-9bbe-4e2f-9457-dd671918563a)


# Argo CD use case to update replicas in github and see how it is synchronizing in EKS  

Modifying spec:

Changing replicas: 3 to replicas:5 in flask-deployment.yaml and commited in Git,  and checking whether it is reflecting or not. 

After updation, count got increased to 5

![image](https://github.com/user-attachments/assets/225595de-931d-4e29-95b4-cd4f616a5413)


Another scenario, Changing postgres replicas from 1 to 2  ![image](https://github.com/user-attachments/assets/d5236492-0be8-43da-bf2b-83f8934cb498)  

![image](https://github.com/user-attachments/assets/e6e98b32-2fd6-437a-83e6-f4ddb63f1198)

After updating to 2  

![image](https://github.com/user-attachments/assets/6fbd4624-3f2b-4034-99dd-ea546e421d6e)



Finally run eksctl delete cluster — name flask-cluster — region us-east-1 to delete the cluster

![image](https://github.com/user-attachments/assets/4a06baf5-1c14-4369-861f-c27d62193bfe)















































