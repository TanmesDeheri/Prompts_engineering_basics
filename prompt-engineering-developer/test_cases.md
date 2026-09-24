Using **Jest + Supertest** with the Express API from the previous step:

```javascript
// tests/taskRoutes.test.js

const request = require("supertest");
const app = require("../app");

// Mock authentication middleware if your application requires req.user.
jest.mock("../middleware/auth", () => {
    return (req, res, next) => {
        req.user = { id: 1 };
        next();
    };
});

describe("Task Tracker API", () => {

    // Test Case 1: Successful task creation
    test("should create a new task successfully", async () => {
        const response = await request(app)
            .post("/api/v1/tasks")
            .send({
                title: "Complete QA testing",
                description: "Test the task creation endpoint",
                due_date: "2026-10-01"
            });

        // Task creation should return HTTP 201 Created.
        expect(response.statusCode).toBe(201);

        // Verify that the response contains the created task.
        expect(response.body).toHaveProperty("data");
        expect(response.body.data).toHaveProperty("id");
        expect(response.body.data.title).toBe("Complete QA testing");
    });


    // Test Case 2: Getting a task with an invalid/non-existent ID
    test("should return 404 when task ID does not exist", async () => {
        const response = await request(app)
            .get("/api/v1/tasks/999999");

        // A task that does not exist should return HTTP 404.
        expect(response.statusCode).toBe(404);

        // Verify that an appropriate error is returned.
        expect(response.body).toHaveProperty("error");
        expect(response.body.error).toBe("Task not found");
    });

});
```

### Test coverage

| Test Case                    | Endpoint                   | Expected | Assertion                               |
| ---------------------------- | -------------------------- | -------: | --------------------------------------- |
| Successful task creation     | `POST /api/v1/tasks`       |    `201` | `expect(response.statusCode).toBe(201)` |
| Invalid/non-existent task ID | `GET /api/v1/tasks/999999` |    `404` | `expect(response.statusCode).toBe(404)` |

Run with:

```bash
npm test
```

**QA note:** The second test assumes `999999` does not exist in the test database. For a deterministic automated test suite, use an isolated test database or mock the database layer so the test does not depend on existing data.
