## Task Description:

Develop a backend for a Task Management System that allows users to create, edit, and manage their tasks.

### Core Requirements:

1. **Authentication and Authorization:**
   - Use Django Rest Framework (DRF) to implement the API.
   - Users should be able to register, log in, and log out.
   - Implement user registration and authentication using JWT tokens (optional)

2. **Data Models:**

   - **User:**
     - Use Django's default user model or a custom one if additional logic is required.

   - **Project:**
     - Name (name): string, required.
     - Description (description): text, optional.
     - Owner (owner): reference to the user who created the project.
     - Created Date (created_at): automatically set when a project is created.

   - **Task:**
     - Title (title): string, required.
     - Description (description): text, optional.
     - Status (status): choice of predefined values (e.g., "pending", "in progress", "completed").
     - Created Date (created_at): automatically set when a task is created.
     - Updated Date (updated_at): automatically updated when a task is modified.
     - Completion Date (completed_at): set when a task is completed.
     - Priority (priority): choice of predefined values (e.g., "low", "medium", "high").
     - Owner (owner): reference to the user who created the task.
     - Project (project): reference to the project the task belongs to.

3. **Task API:**

   - **Create a Task:**
     - POST request to create a new task. Only authenticated users can create tasks.
   
   - **Retrieve Task List:**
     - GET request to retrieve a list of tasks for the current user.
     - Support filtering by status, priority, date, and project.
   
   - **Retrieve Task Detail:**
     - GET request to obtain detailed information about a specific task.
   
   - **Update a Task:**
     - PUT/PATCH requests to update task information. Only the task owner can edit it.
   
   - **Delete a Task:**
     - DELETE request to remove a task. Only the task owner can delete it.

4. **Project API:**

   - **Create a Project:**
     - POST request to create a new project. Only authenticated users can create projects.

   - **Retrieve Project List:**
     - GET request to retrieve a list of projects for the current user.

   - **Retrieve Project Detail:**
     - GET request to obtain detailed information about a specific project.

   - **Update a Project:**
     - PUT/PATCH requests to update project information. Only the project owner can edit it.

   - **Delete a Project:**
     - DELETE request to remove a project. Only the project owner can delete it.

5. **Validation and Security:**

   - All operations should be accessible only to authenticated users.
   - Access control: only the owner of a task or project can modify or delete it.
   - Data validation (e.g., checking valid values for status and priority).

### Additional Requirements (Optional but Encouraged):

- Implement pagination for task and project lists.
- Support sorting of tasks by different criteria (e.g., creation date or priority).
- Implement tags for tasks to enable categorization.
- Send notifications to users (e.g., via email) when a task's status changes.

## Tech stack

- Git - all changes should be pushed to the repository (as part of review I will create Pull Requests)
- Docker compose - to run DB (example below)
- Postgresql (that will be run in Docker)
- Django as main python web framework
- DRF (Django Rest Framework) - for RESTful API

## Steps for implementation

- install Django locally and get acquainted by official tutorial https://docs.djangoproject.com/en/5.1/intro/tutorial01/
- prepare Data Models
- install Docker and Docker compose, run PSQL and connect your service to the DB
- when models will be ready - install DRF and prepare API endpoint (they can be checked by Postman or Insomnia)
- when the service will be ready - build docker image