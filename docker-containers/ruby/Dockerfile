FROM java:8 as jar-builder
RUN mkdir /app
WORKDIR /app
COPY code-fry /app
RUN ./gradlew clean build

FROM ruby:latest
RUN mkdir /app
WORKDIR /app
COPY --from=jar-builder /app /app

