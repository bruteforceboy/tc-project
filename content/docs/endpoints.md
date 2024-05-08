---
title: "API Endpoints"
weight: 1
draft: false
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
bookSearchExclude: false
---

# API Endpoints for LearnQuest

This document provides a detailed guide to the API endpoints available in the LearnQuest application. Each endpoint's purpose, method type, and basic usage are described below, categorized into functional sections.

## Instructor Applications

This section covers the endpoints related to instructor application processes within LearnQuest.

### Submit Instructor Application

- **Endpoint**: `/apply/`
- **Method**: POST
- **Description**: Allows users to submit an application to become an instructor.

## Courses

Endpoints related to course management are grouped here, from creation to deletion.

### Get All Courses

- **Endpoint**: `/courses/`
- **Method**: GET
- **Description**: Retrieves a list of all available courses.

### Create Course

- **Endpoint**: `/courses/create`
- **Method**: POST
- **Description**: Allows authorized users to create a new course.

### Update Course

- **Endpoint**: `/courses/<str:course_id>/update`
- **Method**: PUT
- **Description**: Allows authorized users to update details of an existing course.

### Delete Course

- **Endpoint**: `/courses/<str:course_id>/delete`
- **Method**: DELETE
- **Description**: Allows authorized users to delete an existing course.

### Preview Course

- **Endpoint**: `/courses/<str:course_id>/preview`
- **Method**: GET
- **Description**: Provides a preview of a course's content.

### Full View Course

- **Endpoint**: `/courses/<str:course_id>/full_view`
- **Method**: GET
- **Description**: Provides a full view of a course, including all sections and materials.

## Sections

This section includes endpoints for managing course sections.

### Create Section

- **Endpoint**: `/courses/create_section`
- **Method**: POST
- **Description**: Allows authorized users to create a new section within a course.

### Update Section

- **Endpoint**: `/courses/update_section`
- **Method**: PUT
- **Description**: Allows authorized users to update an existing section within a course.

### Delete Section

- **Endpoint**: `/courses/delete_section`
- **Method**: DELETE
- **Description**: Allows authorized users to delete an existing section from a course.

## Shopping Cart

Endpoints related to the shopping cart functionalities are outlined here.

### Add Course to Cart

- **Endpoint**: `/cart/add`
- **Method**: POST
- **Description**: Adds a specific course to the user's shopping cart.

### Get Cart

- **Endpoint**: `/cart/get`
- **Method**: GET
- **Description**: Retrieves the contents of the user's shopping cart.

### Remove Course from Cart

- **Endpoint**: `/cart/remove`
- **Method**: DELETE
- **Description**: Removes a specific course from the user's shopping cart.

### Checkout

- **Endpoint**: `/cart/checkout`
- **Method**: POST
- **Description**: Processes the checkout of the courses currently in the user's cart.

## Lessons and Reviews

Details about endpoints for managing lessons and submitting course reviews.

### Create Lesson

- **Endpoint**: `/courses/create_lesson`
- **Method**: POST
- **Description**: Allows authorized users to create a new lesson within a course.

### Update Lesson

- **Endpoint**: `/courses/update_lesson`
- **Method**: PUT
- **Description**: Allows authorized users to update an existing lesson.

### Delete Lesson

- **Endpoint**: `/courses/delete_lesson`
- **Method**: DELETE
- **Description**: Allows authorized users to delete an existing lesson from a course.

### Create Review

- **Endpoint**: `/courses/review`
- **Method**: POST
- **Description**: Allows users to create a review for a course.

### Get Reviews

- **Endpoint**: `/courses/<str:course_id>/reviews`
- **Method**: GET
- **Description**: Retrieves all reviews for a specific course.
