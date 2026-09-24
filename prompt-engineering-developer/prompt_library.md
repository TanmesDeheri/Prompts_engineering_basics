## Least to Most prompt
Act as a Business Analyst. We want to design a backend REST API named 'Task Tracker API'.
First, outline the system architecture scope and write 3 core B2B user stories (for
User Signup, Task Creation, and Task Updates) with acceptance criteria. Do not write database schemas or backend code yet.

Save the response in a text file.

## SQL Schema Design Prompt
[CONTEXT]: We are building the database layer for our Task Tracker API.
[ACTION]: Generate relational SQL table schemas matching the database requirements:
- Table 'users': columns for id (primary key), name, email (unique), password_hash, and
created_at.
- Table 'tasks': columns for id (primary key), user_id (foreign key referencing users),
title, description, status, due_date, and created_at.
[REQUIREMENTS]:
- Include SQL constraints (NOT NULL, UNIQUE, FOREIGN KEY, PRIMARY KEY).
- Provide raw DDL SQL code block.

## Generating Route Controller Prompts(CRISPE framework)
- CAPACITY: Act as a Senior Backend Software Engineer.
- RECIPIENT: Junior QA and developer team.
- INSTRUCTION: Write API route controller logic in Node.js (using Express) or Python
(using FastAPI) to handle:
1. POST /api/v1/tasks (Create a new task, extracting title, description, due_date).
2. GET /api/v1/tasks/:id (Read a specific task by ID).
- STYLE: Follow DRY and SOLID design principles. Include clean error handling.
- PARAMETERS: Use raw SQL queries matching the schemas created in Step 3. Do not use an
ORM.
- EVALUATION: Write inline comments explaining how parameters are parsed.

## Secure Reflection Prompt
// Vulnerable Express Route
app.post('/api/v1/login', (req, res) => {
let query = "SELECT * FROM users WHERE email = '" + req.body.email + "' AND
password = '" + req.body.password + "'";
db.query(query, (err, result) => {
if (err) throw err;
res.send(result);
});
});

Act as a Security Auditor. Scan the code block below for security vulnerabilities (e.g.
SQL Injection, unhandled crashes).
[CODE TO AUDIT]:
[Insert the Vulnerable Express Route code above]
Identify the issue, explain the risk, and write a refactored, secure version of this
endpoint using parameterized SQL queries and try/catch blocks.

## Swagger Documentation Prompt
Generate Swagger/OpenAPI yaml documentation for the two endpoints:
- POST /api/v1/tasks
- GET /api/v1/tasks/:id
Include request schema, 200 success response block, and 400 error response blocks.

## Unit Test Prompt
Act as a QA Automation Engineer. Write 2 unit tests in Jest/Supertest (or Python
PyTest) to validate:
- Test Case 1: Successful task creation (asserts status 201).
- Test Case 2: Getting task with invalid ID (asserts status 404).
