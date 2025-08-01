# Environment Configuration for Plane

This document explains how to configure the environment variables for the Plane application using the updated docker-compose.yml file.

## Overview

The updated docker-compose.yml file uses explicit environment variables instead of env_file references. This approach provides better flexibility and clarity in configuration management.

## Setup Instructions

1. Copy the .env.example file to create your own .env file:
   ```bash
   cp .env.example .env
   ```

2. Customize the values in the .env file according to your environment requirements.

3. Run the application using docker-compose:
   ```bash
   docker-compose up -d
   ```

## Environment Variables

### General Settings
- `APP_DOMAIN`: The domain where the application will be hosted
- `APP_RELEASE`: The release version of the application
- `SSL`: Whether to use SSL (true/false)

### Service Configuration
- `*_REPLICAS`: Number of replicas for each service (web, space, admin, api, worker, beat-worker, live)

### Port Configuration
- `LISTEN_HTTP_PORT`: HTTP port to listen on (default: 80)
- `LISTEN_HTTPS_PORT`: HTTPS port to listen on (default: 443)

### URL Configuration
- `API_BASE_URL`: Base URL for the API service
- `WEB_URL`: Base URL for the web application
- `ADMIN_BASE_URL`: Base URL for the admin application
- `SPACE_BASE_URL`: Base URL for the space application
- `LIVE_BASE_URL`: Base URL for the live application
- `APP_BASE_URL`: Base URL for the main application

### Path Configuration
- `API_BASE_PATH`: Base path for the API service
- `ADMIN_BASE_PATH`: Base path for the admin application
- `SPACE_BASE_PATH`: Base path for the space application
- `APP_BASE_PATH`: Base path for the main application
- `LIVE_BASE_PATH`: Base path for the live application

### Debug Settings
- `DEBUG`: Enable/disable debug mode (0/1)
- `CORS_ALLOWED_ORIGINS`: Comma-separated list of allowed CORS origins

### Database Configuration
- `POSTGRES_USER`: PostgreSQL username
- `POSTGRES_PASSWORD`: PostgreSQL password
- `POSTGRES_HOST`: PostgreSQL host
- `POSTGRES_DB`: PostgreSQL database name
- `POSTGRES_PORT`: PostgreSQL port
- `DATABASE_URL`: Full database connection URL

### Redis Configuration
- `REDIS_HOST`: Redis host
- `REDIS_PORT`: Redis port
- `REDIS_URL`: Full Redis connection URL

### RabbitMQ Configuration
- `RABBITMQ_HOST`: RabbitMQ host
- `RABBITMQ_PORT`: RabbitMQ port
- `RABBITMQ_USER`: RabbitMQ username
- `RABBITMQ_PASSWORD`: RabbitMQ password
- `RABBITMQ_VHOST`: RabbitMQ virtual host
- `AMQP_URL`: Full AMQP connection URL

### Storage Configuration
- `USE_MINIO`: Whether to use MinIO (0/1)
- `AWS_REGION`: AWS region
- `AWS_ACCESS_KEY_ID`: AWS access key ID
- `AWS_SECRET_ACCESS_KEY`: AWS secret access key
- `AWS_S3_ENDPOINT_URL`: S3 endpoint URL
- `AWS_S3_BUCKET_NAME`: S3 bucket name
- `FILE_SIZE_LIMIT`: Maximum file size limit in bytes

### Security Configuration
- `SECRET_KEY`: Django secret key
- `ALLOWED_HOSTS`: Comma-separated list of allowed hosts

### Gunicorn Configuration
- `GUNICORN_WORKERS`: Number of Gunicorn workers

### Live Server Configuration
- `LIVE_SERVER_SECRET_KEY`: Secret key for the live server
- `LIVE_PORT`: Port for the live server
- `LIVE_HOSTNAME`: Hostname for the live server

### Cleanup Configuration
- `HARD_DELETE_AFTER_DAYS`: Number of days after which to hard delete files

### SSL Configuration
- `MINIO_ENDPOINT_SSL`: Whether to use SSL for MinIO endpoint (0/1)

### API Rate Limiting
- `API_KEY_RATE_LIMIT`: Rate limit for API keys (format: requests/period)