Large assets like datasets or AI model weights should not be downloaded on every ephemeral function cold start, as this incurs massive latency and bandwidth penalties.

You need to implement a state management script that downloads a large 5GB dummy dataset to a Modal Volume and accesses it in subsequent function calls. Create one remote function that mounts a volume to `/data`, downloads the file only if it is missing, and commits the state; then create a second remote function that mounts the same volume, reads the first 100 bytes of the file, and returns the string.

**Constraints:**
- You MUST configure and attach a `modal.Volume` to both remote functions using the `volumes={"/data": volume}` argument in the function decorators.
- You MUST explicitly handle state persistence (e.g., using `volume.commit()`) after writing the dataset to the volume.
- Do NOT download the dataset if it already exists within the persistent volume.