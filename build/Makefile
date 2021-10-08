TAG=typeorm-sample
NAME=typoorm
IMAGE=$(TAG)
HOST=0.0.0.0
PORT=15432


all: build

build: build-container run-container

build-container:
	docker build -t $(TAG) .

run-container:
	docker run -d -h $(HOST) -p $(PORT):5432 --name $(NAME) $(IMAGE)
	@echo "\nPlease connect typeorm-sample container by \"psql -h $(HOST) -p $(PORT) typoorm typoorm\""

clean:
	-docker stop $(shell docker ps -a -f NAME=$(NAME) -q)
	-docker rm $(shell docker ps -a -f NAME=$(NAME) -q)
	-docker rmi $(TAG)
	-docker volume prune -f
