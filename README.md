# Doctor Appointments Microservices Application

## Project Overview

This is a microservices-based web application for managing doctor appointments. The application is built using a microservices architecture with separate services for doctors, appointments, and a frontend, designed to be deployed using Docker and Kubernetes.

## Architecture

The application consists of four main services:
- **Frontend Service**: Node.js Express application
- **Doctors Service**: Python Flask microservice
- **Appointments Service**: Python Flask microservice
- **Database**: MySQL (for persistent storage)

### Services Details

#### Frontend Service
- Runs on port 3000
- Serves a web interface with two tabs: Doctors and Appointments
- Communicates with Doctors and Appointments services via API calls

#### Doctors Service
- Runs on port 9090
- Provides REST endpoints to retrieve doctor information
- Maintains a list of doctors with their details

#### Appointments Service
- Runs on port 7070
- Provides REST endpoints to retrieve appointment information
- Maintains a list of appointments with doctor and rating details

## Technologies Used

- **Frontend**: Node.js, Express, Axios
- **Backend Services**: Python, Flask
- **Containerization**: Docker
- **Orchestration**: Kubernetes
- **CI/CD**: GitHub Actions

## Prerequisites

- Docker
- Kubernetes
- npm
- Python 3.9
- GitHub account (for CI/CD)

## Local Development Setup

1. Clone the repository
```bash
git clone [Doctors-Appointment-App](https://github.com/ameerahaider/Doctors-Appointment-App)
cd doctor-appointments-app
```

2. Build and run services using Docker Compose
```bash
docker-compose up --build
```

3. Access the application
- Frontend: `http://localhost:3000`

## Deployment

### Docker Deployment
The application uses Docker Compose for local deployment. Each service has its own Dockerfile:
- `frontend/Dockerfile`
- `doctors/Dockerfile`
- `appointments/Dockerfile`

### Kubernetes Deployment
Kubernetes deployment configurations are available in `k8s/` directories for each service.

## CI/CD Pipeline

The project uses GitHub Actions for continuous integration and deployment:
- `.github/workflows/frontend.yml`
- `.github/workflows/doctors.yml`
- `.github/workflows/appointments.yml`

Each workflow:
- Builds Docker images
- Pushes images to Docker Hub
- Updates version in `.env` file

## Environment Variables

Configuration is managed through `.env` file:
- `FRONTEND_VERSION`
- `APPOINTMENTS_VERSION`
- `DOCTORS_VERSION`
- `DOCKER_USERNAME`

## Features

- View list of doctors
- View list of appointments
- Responsive web interface
- Tab-based navigation
- Microservices architecture
- Containerized deployment
