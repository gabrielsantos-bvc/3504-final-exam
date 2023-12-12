
# 3504 - Final Exam

Case Scenario: Upgrading TechCo Company's Website with Dockeriza=on

Gabriel Santos

# Instructions

This project uses AWS EC2 and DockerHub.

## Setting up AWS EC2

* Create a EC2 instance on AWS CONSOLE.
* Create a KEY PAIR .pem to access the instance.
* Change the Security Group to allow SSH and HTTP access.

### Installing Docker

On your EC2 instance run the following commands to install the Docker.

```bash
  sudo yum install -y docker
```

Make sure the Docker service is running.

```bash
  sudo sercice docker start
```

## DockerHub

Create a [DockerHub](https://hub.docker.com/) account if you haven't yet.

## Workflow

To run the workflows you need to create the following secrets on you repository.
To create the secrets go to `Settings` tab of your repository, find the section `Secrets and Variables` and then option `Actions`
click on `New repository secret`.

Username of DockerHub - `DOCKERHUB_USER`\
Password of DockerHub - `DOCKERHUB_PWD`\
Desired Docker Image name - `DOCKERHUB_IMAGE`\
Desired Container name - `CONTAINER_NAME`\
Public IP from EC2 - `EC2_PUBLIC_IP`\
Username of the instance - `EC2_USER`\
Content of your .pem generated when creating the EC2 - `SSH_PRIVATE_KEY`

## How it work
After every push to the main branch the GitHub Actions will generate the Docker Image,
push it to DockerHub and then download the image on EC2 and build the container.
