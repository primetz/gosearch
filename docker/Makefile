SHELL := /bin/bash
DOCKER_COMPOSE_FILE_PATH = ./compose.yaml
DOCKER_COMPOSE_OVERRIDE_FILE_PATH = ./compose.override.yaml
GO_DEV_CONTAINER = gosearch.dev
ZSH_SHELL = zsh

.PHONY: up down drop prune exec-go

up:
	@docker compose up -d --build
	@docker exec -ti $(GO_DEV_CONTAINER) $(ZSH_SHELL)

down:
	@docker compose rm -fsv

drop:
	@docker image prune -af
	@docker network prune -f
	@docker volume prune -f

prune:
	@docker system prune -af --volumes


exec-go:
	@docker exec -ti $(GO_DEV_CONTAINER) $(ZSH_SHELL)
