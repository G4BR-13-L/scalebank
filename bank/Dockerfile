# Build Stage
FROM maven:3.9.3-eclipse-temurin-20-alpine AS build
COPY src /home/app/src
COPY pom.xml /home/app
RUN mvn -f /home/app/pom.xml package

# Execution Stage
FROM openjdk:20-oracle
COPY --from=build /home/app/target/bank-0.0.1-SNAPSHOT.jar /usr/local/lib/bank-0.0.1-SNAPSHOT.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/usr/local/lib/bank-0.0.1-SNAPSHOT.jar"]