# Dockerized Nginx Web Server

This repository contains a Dockerized Nginx web server that serves a simple HTML page.

## Files

* `index.html`: A plain HTML page that displays "Hello, Docker!".
* `nginx.conf`: An Nginx configuration file that serves the `index.html` page.
* `Dockerfile`: A Dockerfile that defines the Docker image.

## Steps to build and run the Docker container

1. Build the Docker image by running `docker build -t my-nginx-image .`
2. Run the Docker container by running `docker run -p 8080:80 my-nginx-image`
3. Access the web server by visiting `http://localhost:8080` in your web browser.

## Public Repository
1. Create a public repository in AWS ECR.   
2. Authenticate Docker to the AWS ECR:
   ``` 
   aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <account_id>.dkr.ecr.<region>.amazonaws.com
   ``` 
4. Tag the Docker Image:    
   `docker tag my-nginx-image:latest <account_id>.dkr.ecr.<region>.amazonaws.com/my-nginx-image:latest`    
5. Push the Image to ECR:    
   `docker push <account_id>.dkr.ecr.<region>.amazonaws.com/my-nginx-image:latest`         
