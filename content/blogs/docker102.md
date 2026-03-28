+++
title = "Docker 102: A Beginner's Guide to Containerisation"
date = 2024-03-14T12:00:00+05:30
type = "post"
description = "A Beginner's Guide to Containerisation"
in_search_index = true
[taxonomies]
tags = ["docker", "virtualization"]
[extra]

+++

Introduction

Docker has emerged as a game-changer, revolutionizing the way applications are built, shipped, and run. Docker simplifies the process of containerization, enabling developers to package their applications and dependencies into lightweight, portable containers. In this beginner's guide, we'll explore the basics of Docker, its fundamental commands, and the role of Docker Compose in orchestrating multi-container applications.

Understanding Docker

A Paradigm Shift While virtual machines provided a significant leap forward in application deployment, they also introduced complexities such as high resource overheads and dependency management issues. Docker emerged as a solution to these challenges by introducing containerization - a lightweight, portable approach to packaging and deploying applications along with their dependencies. At its core, Docker is an open-source platform that allows developers to create, deploy, and manage applications using containers. But what exactly are containers? Think of them as isolated environments that encapsulate an application and all its dependencies, ensuring consistency and portability across different environments. Unlike traditional virtual machines, containers share the host system's kernel, making them lightweight and efficient.

Basic Concepts of Docker:

Docker Images: Blueprints of containers, encapsulating an application, its dependencies, and runtime environment.

Containers: Isolated instances created from Docker images, running applications consistently across different environments.

Dockerfile: Instructions for building Docker images, specifying the base image, dependencies, and runtime configurations.

Docker Commands: Interface for interacting with Docker, including building, running, and managing containers.

Dockerfile: A Dockerfile serves as a blueprint for building Docker images. Let's create a simple Dockerfile for a Python application:

### Use the official Python base image
```bash
FROM python:3.9-slim
```

### Set the working directory in the container
```bash
WORKDIR /app
```

### Copy the current directory contents into the container at /app
```bash
COPY . /app
```

### Install any dependencies specified in requirements.txt
```bash
RUN pip install -r requirements.txt
```

### Specify the command to run on container startup
```bash
CMD ["python", "app.py"]
```

In this Dockerfile:

We start with the official Python base image.

Set the working directory inside the container to /app.

Copy the current directory (which contains our Python application files) into the container.

Install dependencies specified in requirements.txt.

Finally, specify the command to run when the container starts (app.py in this case).

Docker Commands: Getting Started: Now, let's walk through some basic Docker commands:

Build the Docker image:
```bash
docker build -t my-python-app
```

Run the Docker container:
```bash
docker run my-python-app
```

List running containers:

docker ps

View container logs:

```bash
docker logs <container_id>
```

Docker Compose: Managing Multi-Container Applications: Docker Compose simplifies the management of multi-container Docker applications. Let's create a docker-compose.yml file for our Python application:

```bash
version: '3'
services:
  app:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/app
```

In this docker-compose.yml file:

We define a service named app.

Build the Docker image using the current directory (.).

Expose port 5000 to access the application.

Mount the current directory into the container to enable live code reloading during development.

To run the application using Docker Compose:

docker-compose up

Conclusion

Docker simplifies the process of software development and deployment by providing a consistent and isolated environment for applications. With its intuitive commands and powerful features like Docker Compose, developers can streamline their workflows, improve collaboration, and deploy applications with confidence. Whether you're building a simple web app or a complex microservices architecture, Docker is an essential tool in modern day development.
