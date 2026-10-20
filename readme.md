# Module 7 - QR Code Generator

## Project Description

This project is a QR Code Generator created for Module 7 of IS 601. The application uses Python to generate QR codes and Docker to containerize and run the application. This project also uses GitHub Actions for automated Docker image building and DockerHub to store the Docker image.

## Technologies Used

- Python
- Docker
- Docker Compose
- Git
- GitHub
- GitHub Actions
- DockerHub
- Visual Studio Code

## Project Setup

Clone the repository:

```bash
git clone git@github.com:kevinnbravo9/QR-Code-Generator-Module7.git
```

Enter the project directory:

```bash
cd QR-Code-Generator-Module7
```

Create and activate a Python virtual environment:

```bash
/usr/bin/python3 -m venv venv
source venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Run the Application with Python

Run the QR Code Generator:

```bash
python main.py
```

The generated QR code will be saved in the `qr_codes` directory.

## Docker

Build the Docker image:

```bash
docker build -t qr-code-generator-app .
```

Run the application inside a Docker container:

```bash
docker run --rm qr-code-generator-app
```

## Docker Compose

The application can also be run using Docker Compose:

```bash
docker compose up
```

The `qr_codes` directory is mounted so generated QR codes can be saved outside the container.

## GitHub Actions

This project includes a GitHub Actions workflow located in:

```text
.github/workflows/docker.yml
```

The workflow automatically checks that the Docker image builds successfully when changes are pushed to the `main` branch or when a pull request is created.

## DockerHub

The Docker image is available on DockerHub under:

```text
kevinbravor99/qr-code-generator-app
```

The image can be pulled using:

```bash
docker pull kevinbravor99/qr-code-generator-app:latest
```

It can then be run using:

```bash
docker run --rm kevinbravor99/qr-code-generator-app:latest
```

## Security

The Dockerfile uses a slim Python base image and runs the application as a non-root user. The required directories are assigned to the non-root user to help improve container security.
