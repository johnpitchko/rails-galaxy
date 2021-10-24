---
toc: true
title: Cookbook
layout: single
published: false

---
## Refreshing images used in an orchestration

Rebuilding a Docker image does not mean that the new image will be instantiated when the container group launches. Docker Compose must be instructed to recreate images assigned to containers.

    docker compose up --force-recreate --build -d
    docker image prune -f