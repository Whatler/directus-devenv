# Directus Development Environment

This project sets up a development environment for Directus, allowing you to develop extensions, templates, and the Directus app itself. The environment uses Docker to manage services such as Directus, Redis, PostgreSQL, Node.js, and Nginx.

## Services

- **Directus**: The core Directus application.
- **Redis**: Used for caching.
- **PostgreSQL**: The database for Directus.
- **Node.js**: For running custom extensions.
- **Nginx**: As a reverse proxy for Directus.

## Setup

1. **Install Docker**: Ensure Docker is installed on your system. You can use the provided `install.sh` script to install Docker on Ubuntu.

2. **Environment Variables**: Copy the template environment files and fill in the required values.
```sh
cp env/redis.template.env env/redis.env
cp env/postgres.template.env env/postgres.env
cp env/directus.template.env env/directus.env
cp .template.env .env
cp conf/redis.template.conf conf/redis.conf
cp conf/nginx.template.conf conf/nginx.conf
```

3. **Start the Services**: Use Docker Compose to start all the services.
```sh
docker compose up -d
```

## Development

- **Extensions**: Place your Directus extensions in the `extensions` directory.
- **Templates**: Place your Directus templates in the `templates` directory.
- **Directus Configuration**: Modify the Directus configuration in the `env/directus.env` file.

## Stopping the Services

To stop the services, run:
```sh
docker compose down
```

## Additional Information

- **Volumes**: Data for Redis and PostgreSQL is stored in Docker volumes to persist between restarts.
- **Health Checks**: Health checks are configured for Redis and PostgreSQL to ensure they are running correctly.

For more information on Directus, visit the [Directus documentation](https://docs.directus.io/).
