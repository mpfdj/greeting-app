docker swarm init
docker node ls
docker stack deploy -c docker-stack.yml greeting-app
docker stack ls
docker stack ps greeting-app

docker stack rm greeting-app
docker swarm leave --force

# Remove all containers
docker rm $(docker ps --filter status=exited -q)
docker container ls -a

# Create an interactive BASH shell
docker exec -it CONTAINER_ID bash