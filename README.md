## steps

1. build Docker image
    `docker build -t my_selenium .`
2. Taged your docker image
    `docker tag my_selenium:latest <ECR repository URI>:latest`
3. Login your ECR 
    `aws ecr get-login-password | docker login --username AWS --password-stdin <ECR repository URI>`
4. Push to ECR
    `docker push <ECR repository URI>:latest`
5. Create Lambda From container image