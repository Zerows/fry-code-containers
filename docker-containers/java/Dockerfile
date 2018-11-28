FROM java:latest
RUN mkdir /app
WORKDIR /app
COPY code-fry /app
CMD ["javac", "src/main/kotlin/Main.kt"]



# docker build --tag java-fry -f docker-containers/java/Dockerfile .
# docker run -it java-fry:latest bash


