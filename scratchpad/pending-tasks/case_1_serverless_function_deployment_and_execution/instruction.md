Offloading computationally heavy tasks to the cloud allows developers to bypass the resource limitations of their local machines. 

You need to write a Modal script that defines an App named `prime-calculator` and calculates all prime numbers up to 10,000 remotely. Define a remote Python function to perform the mathematical calculation, and trigger this function from your local development environment, ultimately printing the total count of prime numbers found.

**Constraints:**
- You MUST use the `@app.function` decorator to wrap the remote calculation logic.
- You MUST use the `@app.local_entrypoint()` decorator to trigger the remote function and print the results locally.
- Do NOT perform the prime number calculation within the local entrypoint itself.