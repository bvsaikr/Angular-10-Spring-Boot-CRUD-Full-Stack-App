FROM FROM eclipse-temurin:21-jdk-jammy AS build
WORKDIR /app
COPY pom.xml /app/
COPY src /app/src
RUN mvn clean package -D -DskipTests

FROM eclipse-temurin:21-jre-jammy
WORKDIR /app
COPY /target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar",  "app.jar"]
