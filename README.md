# Laravel Project

A Laravel application with Docker support.

## Requirements

- PHP >= 8.1
- Composer
- Node.js & NPM
- Docker & Docker Compose (optional)

## Installation

```bash
# Install PHP dependencies
composer install

# Copy environment file
cp .env.example .env

# Generate app key
php artisan key:generate

# Install JS dependencies
npm install

# Run migrations
php artisan migrate

# Start dev server
npm run dev
php artisan serve
```

## Docker

```bash
# Development
docker compose -f compose.dev.yaml up -d

# Production
docker compose -f compose.prod.yaml up -d
```

## Testing

```bash
php artisan test
```
