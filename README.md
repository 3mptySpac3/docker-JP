# Docker Challenges Overview

---

This project consists of two primary challenges designed to introduce the fundamentals of Docker, containerization, and deploying web applications using Nginx as a reverse proxy. It aims to provide hands-on experience with Dockerfiles, Docker Compose, and the overall process of building and running Docker containers.

## Getting Started

---

### Prerequisites

Before beginning with this project, ensure you have the following installed on your system:

- Docker
- Git (for cloning this repository)
- A text editor or IDE of your choice (e.g., Visual Studio Code)

### Installation

---

1. **Clone this repository:**

   ```bash
   gh repo clone 3mptySpac3/docker-JP
   cd docker-JP
   ```

## Challenge 1: Static Web Server

---

Navigate to the `challenge1` directory.

```bash
cd challenge1
```

Build the Docker image:

```bash
docker build -t <replacthisename>/webserver .
```

Run the Docker container:

```bash
docker run --name mywebserver -d -p 8080:80 <replacethisname>/webserver
```

Access the web server at:

```bash
http://localhost:8080
```

## Challenge 2: Dynamic Node.js Application

---

Ensure Docker Compose is installed and navigate to the `challenge2` directory.

```bash
cd challenge2
```

Start the services defined in `docker-compose.yml`:

```bash
docker-compose up --build
```

Access the Node.js application at:

```bash
http://localhost:8080/api/books
```

## Stopping the Project

---

To stop and remove the containers, networks, and all the resources created by `docker-compose up`, run:

```bash
docker-compose down
```

To stop individual containers started with `docker run`, use:

```bash
docker stop mywebserver
```

And to remove them:

```bash
docker rm mywebserver
```

Replace `<yourname>/webserver` with your Docker Hub username or any name you prefer for your Docker image. This will ensure consistency with your Docker image naming conventions.

## Understanding the Project Structure

---

This project is structured into two main directories, each representing a challenge:

- `challenge1/`: Contains a Dockerfile and a `public` folder. The Dockerfile sets up an Nginx server that serves static content from the `public` directory.
- `challenge2/`: Includes a Dockerfile for a Node.js application and a `docker-compose.yml` file for running the Node.js app alongside Nginx, which acts as a reverse proxy.

Each directory contains all necessary files to build and run the Docker containers for the respective challenge.

## Best Practices

---

Here are some Docker best practices followed in this project:

- **Dockerfile Optimization:** Dockerfiles are optimized for build efficiency and size. For instance, chaining commands to reduce the number of layers in the image.
- **Use of `.dockerignore`:** To avoid unnecessarily copying files into the Docker context, thereby speeding up the build process and minimizing image size.
- **Non-root User:** Where applicable, especially for the Node.js application, running the application as a non-root user enhances security.

---

Read [Docker Documentation](Docker.Documentation.pdf) for more details.
