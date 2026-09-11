# Environment

## MVP Runtime
- API service
- Background worker(s)
- PostgreSQL
- Redis
- Optional object storage

## Local Development
Use Docker Compose for shared services and environment variables for provider credentials.

## Secrets
Keep API keys and tokens outside the repository and inject them only on the server/runtime side.
