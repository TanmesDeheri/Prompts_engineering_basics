openapi: 3.0.3

info:
  title: Task Tracker API
  version: 1.0.0
  description: REST API for creating and retrieving tasks.

servers:
  - url: http://localhost:3000

paths:
  /api/v1/tasks:
    post:
      summary: Create a new task
      operationId: createTask
      tags:
        - Tasks

      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateTaskRequest'

      responses:
        '200':
          description: Task created successfully
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/TaskResponse'

        '400':
          description: Invalid request
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorResponse'

  /api/v1/tasks/{id}:
    get:
      summary: Get a task by ID
      operationId: getTaskById
      tags:
        - Tasks

      parameters:
        - name: id
          in: path
          required: true
          description: Unique identifier of the task
          schema:
            type: integer
            format: int64
            minimum: 1

      responses:
        '200':
          description: Task retrieved successfully
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/TaskResponse'

        '400':
          description: Invalid task ID
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorResponse'

components:
  schemas:

    CreateTaskRequest:
      type: object
      required:
        - title
      properties:
        title:
          type: string
          description: Title of the task
          example: Complete API testing

        description:
          type: string
          description: Detailed description of the task
          example: Test all Task Tracker API endpoints

        due_date:
          type: string
          format: date
          nullable: true
          description: Task due date
          example: '2026-10-01'

    Task:
      type: object
      properties:
        id:
          type: integer
          format: int64
          example: 101

        user_id:
          type: integer
          format: int64
          example: 5

        title:
          type: string
          example: Complete API testing

        description:
          type: string
          nullable: true
          example: Test all Task Tracker API endpoints

        status:
          type: string
          example: pending

        due_date:
          type: string
          format: date
          nullable: true
          example: '2026-10-01'

        created_at:
          type: string
          format: date-time
          example: '2026-09-24T14:30:00Z'

    TaskResponse:
      type: object
      properties:
        data:
          $ref: '#/components/schemas/Task'

    ErrorResponse:
      type: object
      required:
        - error
      properties:
        error:
          type: string
          example: Invalid task ID
