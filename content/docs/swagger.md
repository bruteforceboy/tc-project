---
title: "Swagger API Documentation"
weight: 3
draft: false
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
bookSearchExclude: false
---

# Swagger API Documentation for LearnQuest

This document provides the Swagger (OpenAPI) definitions for key endpoints within the LearnQuest application. It aims to help developers understand the structure of the API and facilitate integration with other systems.

## OpenAPI Specification

The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to RESTful APIs which allows both humans and computers to discover and understand the capabilities of the service without access to source code, documentation, or through network traffic inspection.

### Version Information

- **OpenAPI Version**: 3.0.3
- **Title**: LearnQuest API
- **Version**: 1.0.0

### Servers

- **URL**: `https://api.learnquest.com`
- **Description**: Production server

## Endpoint Definitions

### Submit Instructor Application

```yaml
paths:
  /apply/:
    post:
      summary: "Submit an instructor application"
      description: "Allows users to submit an application to become an instructor on LearnQuest."
      operationId: "submitApplication"
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                name:
                  type: string
                  example: "John Doe"
                email:
                  type: string
                  format: email
                  example: "john.doe@example.com"
                bio:
                  type: string
                  example: "Experienced software developer..."
      responses:
        '201':
          description: "Application submitted successfully."
        '400':
          description: "Invalid input, object invalid."
```

##  Get All Courses

```yaml
paths:
  /courses/:
    get:
      summary: "Retrieve all courses"
      description: "Fetches a list of all courses available on LearnQuest."
      operationId: "getAllCourses"
      responses:
        '200':
          description: "A list of courses successfully retrieved."
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Course'
```

## Create Course

```yaml
components:
  schemas:
    Course:
      type: object
      properties:
        id:
          type: string
          format: uuid
          description: "Unique identifier for the course"
        title:
          type: string
          description: "Title of the course"
        description:
          type: string
          description: "Detailed description of the course"
        instructorId:
          type: string
          format: uuid
          description: "Identifier for the instructor of the course"
```

