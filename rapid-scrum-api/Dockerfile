FROM alpine/git as clone
WORKDIR /usr/src
RUN git clone https://github.com/gilmario-kpslow/rapid-scrum-api.git /usr/src

FROM maven:3.5-jdk-8 as compile
WORKDIR /usr/src
COPY --from=clone /usr/src/ /usr/src
RUN mvn clean package -DskipTests

FROM openjdk:8-jre
COPY --from=compile /usr/src/target/rapidscrum-0.0.1-SNAPSHOT.jar /usr/src/app.jar
EXPOSE 8080
WORKDIR /usr/src
CMD java -jar -Dspring.profiles.active=dockerdev  -Djava.net.preferIPv4Stack=true /usr/src/app.jar
