Sequential processing of large batches of I/O bound tasks, such as web scraping, creates massive bottlenecks that can be easily resolved using cloud concurrency.

You need to create a script that checks the HTTP status codes for a provided list of 1,000 sample URLs using Modal's parallel execution capabilities. Define a remote function that takes a single URL and returns a tuple of `(URL, status_code)`, then orchestrate the execution so that dozens of URLs are processed concurrently in the cloud.

**Constraints:**
- You MUST use Modal's `.map()` or `.starmap()` execution methods to distribute the workload concurrently.
- Do NOT iterate over the list of URLs sequentially (e.g., using a standard `for` loop) in the local entrypoint to call the function.
- The final output MUST be a successfully aggregated list of the `(URL, status_code)` results returned to the local machine.