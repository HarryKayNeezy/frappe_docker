### Create the ECR using the Terraform script/via the console for testing

### Upload the docker image to ECR
```sh
<!--    -  aws ecr get-login-password --region eu-west-2${region} | docker login --username AWS --password-stdin ${ACCOUNT_ID}.dkr.ecr.eu-west-2.amazonaws.com -->
  -  aws ecr get-login-password --region eu-west-2 | docker login --username AWS --password-stdin 006374091282.dkr.ecr.eu-west-2.amazonaws.com 
  ```   
  
### Building the Docker image:
```
docker build -t test 
```  

### Tag the built image so that you can upload it to the created repository:
```
docker tag test:latest ${ACCOUNT_ID}.dkr.ecr.YOUR REGION.amazonaws.com/test:latest
```

### Push the image to the AWS repository 
docker push YOUR ID.dkr.ecr.YOUR REGION.amazonaws.com/test:latest

### Create an ECS Fargate Cluster via Terraform/ via the console for testing
###  Create task definitions
###  Create service
