# --- Build Stage ---
FROM maven:3.9.9-eclipse-temurin-21 AS build
WORKDIR /app

COPY pom.xml .
RUN mvn -B dependency:resolve

COPY src ./src
RUN mvn -B package -DskipTests

# --- Runtime Stage ---
FROM eclipse-temurin:21-jre
WORKDIR /app

ENV PORT=8080

COPY --from=build /app/target/*.jar app.jar

CMD ["java", "-jar", "app.jar"]