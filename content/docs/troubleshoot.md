---
title: "Troubleshooting Guide"
date: 2023-05-08T12:00:00Z
draft: false
weight: 6
---

# Troubleshooting Guide for LearnQuest

Experiencing issues with your LearnQuest installation? Don't worry, this guide is designed to help you identify and solve common problems that might arise during the installation and setup process.

## Common Installation Problems and Solutions

### 1. Docker Is Not Running

#### Symptom:
When you try to run `docker-compose up`, you receive an error indicating that Docker is not running.

#### Solution:
Make sure Docker is active on your system. You can start Docker manually by opening the Docker Desktop application. Once it's running, try the `docker-compose up` command again.

### 2. Git Clone Issues

#### Symptom:
Errors during the cloning process such as "repository not found" or "permission denied".

#### Solution:
- Ensure that the URL provided in the clone command is correct: `https://github.com/abuwho/LearnQuest.git`
- If you see "permission denied", check that your SSH keys are set up correctly with GitHub, or use the HTTPS URL as shown above which doesn't require SSH authentication.

### 3. Missing Environment Variables

#### Symptom:
The application starts, but you encounter errors related to the database or other services that indicate missing or incorrect configuration.

#### Solution:
- Double-check that you have created the `docker-backend.env` file in the root directory of the project.
- Ensure that all required environment variables are correctly written in the `docker-backend.env` file. The required variables are:
```bash
  DATABASE_HOST=<your-database-host>
  DATABASE_PASSWORD=<your-database-password>
```

### 4. Docker Compose Up Errors

#### Symptom:
Errors when running `docker-compose up`, such as "services could not be started" or specific service-related errors.

#### Solution:
- Review the error messages in the terminal. They often provide clues about what is wrong.
- Check the Docker Compose file (docker-compose.yml) for any syntax errors or misconfigurations.
- Ensure that all services referenced in the Docker Compose file have their corresponding Dockerfiles and configuration files set up correctly.

### 5. Application Not Loading in Browser

#### Symptom:
After running `docker-compose up`, the application does not load at `http://localhost:8000`.

#### Solution:
- Check that the Docker containers are all running by using `docker ps`. All containers related to the project should be up and running.
- Ensure that port 8000 on your local machine is not being used by another application. If it is, you may need to stop that application or change the port settings in the Docker Compose file.
- Check the application logs by using `docker logs [container_id]` to identify any runtime errors.

### 6. Database Connection Issues

#### Symptom:
Errors related to "database connection failed" when the application tries to connect to the database.

#### Solution:
- Confirm that the database server is running and accessible from where you are running your Docker containers.
- Verify the `DATABASE_HOST` and `DATABASE_PASSWORD` values in your `docker-backend.env` are correct and match the credentials of your database server.
- Ensure that the network settings in Docker allow for communication between your application containers and the database server.

## Additional Help

If you encounter issues not covered in this guide, consider the following resources:
- **LearnQuest GitHub Issues**: Check the Issues page of the LearnQuest repository for similar problems or to post a new issue.
- **Docker Documentation**: For detailed information on using Docker and Docker Compose, visit the Docker official documentation.