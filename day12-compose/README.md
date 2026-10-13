# Docker Compose — Day 12

## Architecture

Flask Web
   |
   +---- PostgreSQL
   |
   +---- Redis

## Services

### web
Flask application on port 5000.

### db
PostgreSQL 16 with persistent named volume.

### redis
Redis 7 used for hit counting.

## Start

docker compose up -d --build

## Check status

docker compose ps

## Test

curl http://localhost:5000/
curl http://localhost:5000/health

## Stop

docker compose down

## Persistence

PostgreSQL data is stored in the pgdata named volume.

## Troubleshooting

docker compose config
docker compose logs
docker compose logs web
