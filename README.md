# End-to-end-ML-Project


## Workflows

1. update config.yaml
2. update schema.yaml
3. update params.yaml
4. update the entity 
5. update the configuration manager in src config
6. update the components
7. update the pipeline
8. update the main.py
9. update the app.py

# How to run?
### STEPS:

1. Creating python virtual environment
```bash
python -m venv venv
```
2. Activate virtual environment
```bash
venv\Scripts\activate
```
3. Install all the requirements
```bash
pip install -r requirements.txt
```
4. Run the Wine Prediction App
```bash
python app.py
```
5. Now, in browser open this link- http://127.0.0.1:8080


# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy Needed for IAM user:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Copy Save the URI Link from Amazon ECR page. 
      e.g.-> 149536498788.dkr.ecr.ap-south-1.amazonaws.com/mlproject

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    Open Github repository>Repository setting>actions>runner>new self hosted runner> choose os> then run command one by one shown there on EC2 Ubuntu console.


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = ap-south-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = wineqp-app

# 8. Initiate CI/CD Pipeline and Run App:
    
    Push the updated code to Git and CI/CD will automatically push your updated code to EC2 Instance.

    Get the app URL from EC2 instance Dashboard page and Run the app.

