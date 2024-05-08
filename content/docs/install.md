---
title: "Installation Guide"
date: 2023-05-08T12:00:00Z
draft: false
---

# Installation Guide for LearnQuest

Welcome to the LearnQuest Installation Guide! This guide will walk you through the steps to get LearnQuest up and running on your computer. Don’t worry if you’re new to some of the terms or tools—we’ll explain everything you need to do.

## What You'll Need Before Starting

Before we begin, you'll need to install a few tools. Here’s what you’ll need:

- **Docker**: This is a tool that allows you to run applications in a loosely isolated environment called a container. You can download it from [Docker's website](https://www.docker.com/products/docker-desktop).
- **Git**: Git is a version control system that lets you track changes to files and coordinate work on those files among multiple people. Download it from [Git's website](https://git-scm.com/downloads).
- **Node.js**: This is optional. If you plan to work on the front-end, you'll need Node.js. It’s a JavaScript runtime that lets you run applications outside a web browser. Download it from [Node.js's website](https://nodejs.org/en/).

## Step-by-Step Installation Instructions

### Step 1: Cloning the Repository
First, we need to get the project files onto your computer. We do this by cloning the repository, which is like downloading but for code projects.

Open your command line interface (CLI), which is Terminal on macOS and Linux or Command Prompt on Windows, and enter the following command:

```bash
git clone https://github.com/abuwho/LearnQuest.git
```

### Step 2: Navigating to the Project Directory
Now that you have the files, you need to move into the project directory. Still in your CLI, type:

```bash
cd LearnQuest
```

### Step 3: Setting Up Environment Variables
Next, we need to set up environment variables. These are like secret keys that your application needs to access various services.

Create a new file for Docker environment settings by typing:

```bash
touch docker-backend.env
```

Then, you need to add database access information to this file. Open docker-backend.env in a text editor and add the following lines (replace `<your-database-host>` and `<your-database-password>` with your actual database host and password):

```bash
DATABASE_HOST=<your-database-host>
DATABASE_PASSWORD=<your-database-password>
```

### Step 4: Running the Application
We’re almost there! Now, we'll use Docker to run the application. Type the following command in your CLI:

```bash
docker-compose up
```

This command starts all the services defined in your Docker configuration, which includes your LearnQuest application.

### Step 5: Verifying the Installation
Once everything is running, open your web browser and visit:

http://localhost:8000

If everything was set up correctly, you should see the LearnQuest application running!