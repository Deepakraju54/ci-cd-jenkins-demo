# CI/CD Jenkins Demo

This is a basic Node.js application to demonstrate a CI/CD pipeline using Jenkins and GitHub.

## Features

- Simple HTTP server
- Jenkins integration
- CI/CD ready

## How to Run

```bash
npm install
npm start
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Node.js CI/CD Pipeline with Jenkins and Docker

This project demonstrates a complete CI/CD pipeline using Jenkins, Docker, and GitHub, hosted on an AWS EC2 instance.

## Features

- Node.js app with npm
- Jenkins pipeline using `Jenkinsfile`
- Dockerized app
- Docker image pushed to Docker Hub
- Hosted on AWS EC2

## Tech Stack

- Node.js
- Jenkins (running on Docker)
- Docker
- GitHub
- AWS EC2

## Setup

### Jenkins Pipeline

1. Jenkins installed via Docker on AWS EC2
2. GitHub repo connected with webhook
3. Jenkinsfile handles:
    - Git clone
    - `npm install`
    - Docker build and tag
    - Docker push (optional)

### Docker Image

Available on Docker Hub:  
[**your-dockerhub-username/node-ci-cd-demo**](https://hub.docker.com/r/your-dockerhub-username/node-ci-cd-demo)

### Run Locally

```bash
docker pull your-dockerhub-username/node-ci-cd-demo:v1
docker run -p 3000:3000 your-dockerhub-username/node-ci-cd-demo:v1
