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


## local test

1. set .env file
2. run docker compose
    `docker compose up --build`
3. curl 
    `curl -XPOST "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{"payload":"hello world!"}'`
4. close the ps 
    `docker compose down`