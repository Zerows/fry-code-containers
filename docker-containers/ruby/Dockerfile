FROM java:8 as jar-builder
RUN mkdir /app
WORKDIR /app
COPY code-fry /app
RUN ./gradlew clean build


FROM alpine:3.7
RUN mkdir /app
WORKDIR /app

RUN apk --update add openjdk8-jre \
            ruby
COPY --from=jar-builder /app /app

RUN mkdir /home/runner
RUN mkdir /home/runner/bin

RUN ln -s /usr/bin/java /home/runner/bin/java
RUN ln -s /usr/bin/javac /home/runner/bin/javac
RUN ln -s /usr/bin/ruby /home/runner/bin/ruby
RUN ln -s /usr/bin/python /home/runner/bin/python
RUN ln -s /usr/bin/node /home/runner/bin/node

ENV PATH=/home/runner/bin
RUN echo $PATH

CMD java -jar build/libs/fry-code-runner-1.0-SNAPSHOT.jar

