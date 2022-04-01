.PHONY: test

args=""

# Absolutely awesome: http://marmelab.com/blog/2016/02/29/auto-documented-makefile.html
help: ## shows this help
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(firstword $(MAKEFILE_LIST)) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-15s\033[0m %s\n", $$1, $$2}'

permissions:
	sudo chown -R ${USER}:${USER} .

permissions-postgres:
	docker-compose exec postgres bash -c "\
		chown -R postgres:postgres /var/lib/postgresql/data \
		&& chmod -R 777 /var/lib/postgresql/data \
	"

build: ## Build all docker images from docker-compose.yml
	mkdir -p var/postgresql var/minio var/minio-config
	sudo chmod -R 777 var
	docker-compose up --build

up: ## Lift containers already built
	docker-compose up

down-up: ## Lift containers already built (down first)
	docker-compose down && docker-compose up

up-d: ## Detached mode: Run containers in the background, print new container names.
	docker-compose up -d

down-up-d: ## Detached mode: Run containers in the background, print new container names. (down first)
	docker-compose down && docker-compose up -d

ps: ## Check containers statuses
	docker-compose ps

recreate: ## Recreate containers even if their configuration and image haven't changed
	docker-compose up --force-recreate

down-recreate: ## Recreate containers even if their configuration and image haven't changed (down first)
	docker-compose down && docker-compose up --force-recreate

down: ## Stop containers and removes containers, networks, volumes, and images created by up.
	docker-compose down

remove-orphans: ## Remove containers for services not defined in the docker-compose file
	docker-compose down --remove-orphans

logs: ## Display log output from services.
	docker-compose logs -f

yarn: ## Run yarn directly in the NodeJS API container. I.e: args=make yarn args="add ts-node -D"
	docker-compose exec api yarn ${args}

yarn-add: ## Run yarn to add packages . I.e: args=make yarn args="ts-node"
	docker-compose exec api yarn add ${args}

yarn-add-d: ## Run yarn to add development packages. I.e: args=make yarn args="add ts-node"
	docker-compose exec api yarn add -D ${args}

execute: ## Run yarn ts-node-dev with files. I.e: args=make execute args=src/authors/create_many.ts
	yarn ts-node-dev ${args}

bash: ## Execute some command directly in the NodeJS API container
	docker-compose exec api ${args}

db-pull: ## Run application migrations
	yarn prisma db pull

migrate: ## Run application migrations
	yarn prisma migrate dev

migrations-generate: ## Generate a migration file with recent changes (diff)
	yarn prisma migrate dev --name ${args}

prisma-studio: ## Open connection to prisma studio
	yarn prisma studio --port 5555 --browser none

prisma-studio-default: ## Open prisma studio in default browser
	yarn prisma studio --port 5555

prisma-studio-browser: ## Open prisma studio in the browser (firefox, chrome, etc.)
	yarn prisma studio --port 5555 --browser ${args}

lint: ## Run lint
	docker-compose exec api yarn lint

test: ## Run tests
	docker-compose exec api yarn test ${args}

test-cov: ## Run tests and generate coverage report
	sudo chmod -R +x cli
	make migrate-e2e
	docker-compose exec api yarn test:cov

e2e-watch: ## Run tests e2e on watching mode
	sudo chmod -R +x cli
	make migrate-e2e
	make yarn args="test:e2e:watch"

e2e: ## Run tests e2e one time
	sudo chmod -R +x cli
	make migrate-e2e
	make yarn args="test:e2e"
