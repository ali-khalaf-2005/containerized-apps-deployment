# Dockerfile Full Lab

A hands-on Docker project that builds a custom Nginx image and runs a static website inside a Docker container.

The goal of this lab is to practice writing a Dockerfile, building images, running containers, publishing ports, and understanding Docker build caching.

## Project Overview

The project packages a static HTML website into a Docker image based on `nginx:alpine`.

The container serves the website over HTTP, making it accessible through a published host port.

## Technologies

- Docker
- Dockerfile
- Nginx
- HTML 
- Docker CLI

## Project Structure

```text
dockerfile-portfolio-lab/
├── Dockerfile
├── index.html
├── .dockerignore
├── README.md
└── screenshots/
    └── website-running.png
```

## Docker Concepts Practiced

- `FROM` — selects the base image.
- `WORKDIR` — sets the working directory for subsequent instructions that use relative paths.
- `COPY` — copies website files into the image.
- `RUN` — executes commands during image building.
- `ENV` — defines environment variables.
- `EXPOSE` — documents the container port used by the application.
- `CMD` — defines the default command used to start the container.
- `.dockerignore` — excludes unnecessary files from the build context.
- Image tags — identifies image versions.
- Port publishing — maps a host port to a container port.
- Build cache — demonstrates how Docker reuses build steps when possible.

## Build the Image

Run these commands from the project directory:

```bash
docker build -t dockerfile-portfolio-lab:1.0 .
```

## Run the Container

```bash
docker run -d \
  --name portfolio-web \
  -p 8080:80 \
  dockerfile-portfolio-lab:1.0
```

Open the website in a browser:

```text
http://localhost:8080
```

## Verify the Container

Check the running container:

```bash
docker ps
```

Inspect the container logs:

```bash
docker logs portfolio-web
```

Inspect the published port:

```bash
docker port portfolio-web
```

## Build Cache Experiment

Rebuild the image without changing any files and observe which steps use the build cache.

Then modify the HTML file and rebuild the image to observe how changes affect subsequent build steps.

Tag a new version of the image and verify the updated website.

## Cleanup

Remove the container when finished:

```bash
docker rm -f portfolio-web
```

Remove the image if it is no longer needed:

```bash
docker image rm dockerfile-portfolio-lab:1.0
```

## Learning Outcome

This project demonstrates practical experience with Docker image creation, container execution, port publishing, image versioning, and build-cache behavior.

It is a learning project intended to demonstrate hands-on Docker practice.
