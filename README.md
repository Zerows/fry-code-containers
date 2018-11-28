# fry-code-containers

docker containers for frying code

## Usefule Commands 
1. git submodule update --recursive --remote
2. docker build --no-cache --tag java-fry -f docker-containers/java/Dockerfile .
3. docker run -it -a stdout java-fry:latest bash -c "java -jar build/libs/fry-code-runner-1.0-SNAPSHOT.jar -c ./input.json"