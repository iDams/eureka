FROM maven:3.5-alpine as builder

COPY routing-service/ /routing-service

RUN cd /routing-service && mvn package -DskipTests

FROM openjdk:8-alpine

COPY --from=builder /routing-service/target/routing-service-0.0.2-SNAPSHOT.jar /opt/routing.jar

CMD java -jar /opt/routing.jar

