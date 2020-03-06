# Docker Training

## What will this training include?
- [ ]	[**Installation/Configuration**](#installation)
- [ ]	[**Containerize Applications**](#containerize-applications)
- [ ]	**Deployment**


## What is Docker?
> Docker is a tool designed to make it easier to create, deploy, and run applications by using containers.

## What are containers?
> A container is a set of one or more processes that are isolated from the rest of the system. All the files necessary to run them are provided from a distinct image, meaning that Linux containers are portable and consistent as they move from development, to testing, and finally to production

## Why use Docker?
> You are able to create, deploy, and move applications/solutions/tools from different environments w/ Docker. The container that you will create will have all of the necessary libraries, dependencies and files needed so that you can go from developmen to production. Docker makes it easier to host applications locally or in the cloud.

> Container images provide portability and version control, helping ensure that what works on a developer’s laptop also works in production

## Containerization v. Virtualization
* Virtualization lets your operating systems (Windows or Linux) run simultaneously on a single hardware system.  
---
* Containers share the same operating system kernel and isolate the application process from the rest of the system.


![ContainerVSVirtualization](container-virtual.png)
*Seeing is believing*

## Getting Started w/ Docker
> Usually we would have an installation step here, but this would take much time. To learn more about getting docker installed please reference the docs at: https://docs.docker.com/get-docker/

## Installation:
#### For this training, we will focus on a Windows based environment:
Navigate to the following link to follow along w/ installation: https://docs.docker.com/docker-for-windows/install/

## Containerize Applications
### What We Will Accomplish
- [ ] **Create A Dockerfile**
- [ ] **Containerize Predifined Application**
- [ ] **Run image as a container**
- [ ] **Access Container locally on port 80**

### Lets access our Docker environments.
#### Three virtual machines have already been set up w/ docker installed. No need for us to download it locally on our computer. To access your specificed virtual machine, I will provide you with the key and you will then run the following command:  
`ssh -i <private_key> vagrant@<IP>`
#### After gaining access, verify that docker is installed w/:
`docker -v`
#### You should see the following output:
```bash
Docker version 19.03.7, build 7141c199a2
```
### Let's Define A Image
To create our own image, we must first define a Dockerfile. A dockerfile is like a recipe for building a cake, but in our instance a image. Defining this file is the first step in containerizing an application.

#### Let's create a simple nginx image that copies files into container and serves a static site.
```yaml
FROM nginx:latest

COPY . .
```
