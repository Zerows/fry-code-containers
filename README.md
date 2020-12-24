# fry-code-containers

docker containers for frying code

## Usefule Commands 
1. docker build --no-cache --tag java-fry -f docker-containers/java/Dockerfile .
2. Test run a javascript runner: docker run -it -a stdout javascript-fry:latest sh -c "java -jar build/libs/fry-code-runner-1.0-SNAPSHOT.jar -c /app/src/test/resources/input_javascript_success.json"

## Create new docker images for new lannguages
1. Create a new folder under docker_containers
2. Link the executable of your language to `/home/runner` eg. (RUN ln -s /usr/bin/java /home/runner/bin/java)
3. Export PATH environmet variable to `ENV PATH=/home/runner/bin`
4. Run the code fry source code which is in java `CMD java -jar build/libs/fry-code-runner-1.0-SNAPSHOT.jar`

