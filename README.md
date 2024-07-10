# Multi-Container Application with Docker, GitHub Actions, and AWS Elastic Beanstalk

## Introduction
This project is a **multi-container application** built using **React** for the frontend, **Node/Express.js** for the backend, **Postgres** for the database, and **Redis** for caching. **Nginx** is used as a **reverse proxy and load balancer**. The primary goal is to **containerize the application using Docker**, automate the **testing and deployment pipeline with GitHub Actions**, and deploy it to **AWS Elastic Beanstalk**.

Note that the redis and postgres services are used only to emulate a real-world scenario where multiple services are involved. The application itself is a simple one that calculates the Fibonacci value of a given number. The goal is to demonstrate the process of containerizing a multi-service application and automate the testing and deployment process.

## Application Architecture

The application consists of the following services:

1. **Client (React):** The frontend of the application built using React.
2. **Server (Node/Express.js):** The backend of the application built using Node.js and Express.js.
3. **Worker (Node):** A worker service built using Node.js that listens to Redis for new values and performs the required computaions. 
4. **Nginx:** A reverse proxy and load balancer that routes requests to the appropriate service.
5. **CI/CD Pipeline:** GitHub Actions is used to automate the testing and deployment process. See the `.github/workflows` directory for the workflow files.



## Requirements
Before running this application, ensure you have the following software installed:

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Install Docker Compose](https://docs.docker.com/compose/install/)

## Running the App Locally
To run the application locally, follow these steps:

1. **Clone the repository:**
   ```bash
    git clone https://github.com/siddharth-mavani/Multi-Docker.git
    cd Multi-Docker
   ```

2. **Build and start the containers:** `bash docker-compose -f docker-compose-dev.yml up --build`

3. **Access the application:** `http://localhost:3050`

## Dockerfiles
There are two kinds of Dockerfiles in the project:
- `Dockerfile.dev`: Used during development for running the application on the local machine.
- `Dockerfile`: Used for deployment.

## Additional Resources
- **Docker Documentation**: [Docker Docs](https://docs.docker.com/)
- **GitHub Actions Documentation**: [GitHub Actions Docs](https://docs.github.com/en/actions)
- **AWS Elastic Beanstalk Documentation**: [AWS Elastic Beanstalk Docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)