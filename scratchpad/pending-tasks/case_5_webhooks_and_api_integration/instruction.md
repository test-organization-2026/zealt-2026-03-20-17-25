Serverless endpoints provide a highly scalable way to expose internal Python functions, logic, and microservices to external client applications.

You need to deploy a serverless web endpoint that acts as a text sanitization microservice. The webhook must accept an incoming HTTP POST request containing a JSON payload with a `text` field, convert the provided text to uppercase to simulate sanitization, and return a standardized JSON response structured as `{"sanitized_text": "..."}`.

**Constraints:**
- You MUST use Modal's `@modal.web_endpoint(method="POST")` decorator (or Modal's direct ASGI/FastAPI integration) to handle the incoming request.
- The endpoint MUST successfully parse incoming JSON data and return a valid JSON response schema.
- Do NOT require authentication tokens to access this specific webhook endpoint.