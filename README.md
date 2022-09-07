# CI/CD Pipeline with AWS

Creating a CI/CD environment by using github actions for automatically deploying a docker container to a ecs cluster having 3 instances behind an application load balancer using dockerhub as a remote repository, triggered by a github push event and integrating with a slack app for automatically notifying upon new builds.

## Requirements :
1. Git
2. Docker
3. Maven

## Initial Steps :
1. Cloning from git repository
2. Build and Tag Docker Image
3. Push the Docker Image to Dockerhub

## Docker Repository :
![image](https://user-images.githubusercontent.com/66320171/188894642-35f5303a-9ec5-4633-81ba-80fdac2b57ef.png)

## Creating ECS Cluster :
![image](https://user-images.githubusercontent.com/66320171/188895639-282cf8ea-f69b-410b-9131-2d7d9be801e5.png)

<img width="456" alt="image" src="https://user-images.githubusercontent.com/66320171/188895714-9e243c29-df13-460c-9e26-87fe24339d05.png">

<img width="751" alt="image" src="https://user-images.githubusercontent.com/66320171/188895999-65754986-a9a6-45d6-975f-a90ccf258449.png">

## Creating Task Definition and adding Container :
![image](https://user-images.githubusercontent.com/66320171/188896249-dfe60847-b784-42cb-8077-e89206b6c9bf.png)

![image](https://user-images.githubusercontent.com/66320171/188896314-1216764d-5cff-4b79-b6b1-2dac854254d6.png)

![image](https://user-images.githubusercontent.com/66320171/188896362-c95067f4-2bed-45b5-8086-189a3ca22c50.png)

## Creating Service :
<img width="528" alt="image" src="https://user-images.githubusercontent.com/66320171/188896451-cd848daf-2fcd-4ec1-8d19-ecbba0f01cb4.png">

## Creating Target Group :
![image](https://user-images.githubusercontent.com/66320171/188896547-aae547a8-7ce2-45e4-8c1f-003ad03d1b94.png)

## Creating Load Balancer :
![image](https://user-images.githubusercontent.com/66320171/188896621-658b0a65-dec5-4765-8393-cb0baa18b006.png)

## Creating Rules for forwarding requests :
![image](https://user-images.githubusercontent.com/66320171/188896719-1c1168cf-240b-4fdc-9cac-956450b5d185.png)

## Setting up Slack Notifications :
![image](https://user-images.githubusercontent.com/66320171/188896905-35da421c-6924-4965-a2df-30e41a2293d8.png)

## Termination of old and Creation of new tasks :
<img width="754" alt="image" src="https://user-images.githubusercontent.com/66320171/188897174-6cf108c9-d879-4252-b3e0-b7ed20a2ba85.png">

<img width="733" alt="image" src="https://user-images.githubusercontent.com/66320171/188897220-2f75caf1-f34d-4eb5-a519-655e818d5455.png">

## Task Event Log :
<img width="808" alt="image" src="https://user-images.githubusercontent.com/66320171/188897296-767a9d6e-cfc7-4a62-88dd-b376e617245f.png">

<img width="809" alt="image" src="https://user-images.githubusercontent.com/66320171/188897343-f1f6eb42-5320-46d1-a71b-e5f1503d5181.png">

![image](https://user-images.githubusercontent.com/66320171/188897378-bb440b7a-6324-4c86-b599-bb1e119d7e62.png)

## Github Actions Log :
![image](https://user-images.githubusercontent.com/66320171/188897460-ac679939-6ec0-4586-b588-433fd38f8951.png)

Notification for build success :
![image](https://user-images.githubusercontent.com/66320171/188897553-beddab1e-f0a1-40dc-ad49-a7618149f7e7.png)

## Final Changes reflecting in the output :
When changes are made in the application and pushed to the github repository, Github actions is triggered and artifacts are generated using Maven. Docker images are then updated in the dockerhub. These are in turn updated in the ECS Cluster having 3 instances behind an application load balancer. After each build a slack notification is received on the subscribed mail id as well as on the app itself. After succesful build, the changes are reflected in the application. 
![image](https://user-images.githubusercontent.com/66320171/188897808-40e024e4-71dd-4be3-85b1-a1dacf6f81c3.png)
