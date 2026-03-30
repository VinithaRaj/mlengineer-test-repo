Explain how you would integrate multiple APIs with different rate limits?

I would design a system with per-API rate limiting, queuing, and centralized orchestration.

Each API would have its own rate limiter (like token bucket or leaky bucket) based on its limits. Requests would be placed into separate queues per API, and worker services would process them while respecting these limits.

To handle throttling, I would implement retry mechanisms with exponential backoff and jitter, and use circuit breakers to temporarily stop calling APIs that are consistently failing. I would also use caching and batching where possible to reduce the number of API calls.

I would add monitoring and observability per API to track rate limit usage, failures, and latency to ensure the system remains stable and efficient under load.