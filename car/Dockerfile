FROM maven:3.9.9-eclipse-temurin-21-alpine AS builder
WORKDIR /app
COPY ./pom.xml ./
COPY ./src ./src
RUN mvn clean package -DskipTests

FROM eclipse-temurin:21-jdk-alpine
WORKDIR /app
ARG JAR_FILE=target/*.jar
COPY --from=builder /app/${JAR_FILE} app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]