# Multi-stage build using Maven + JDK 17
FROM maven:3.9-eclipse-temurin-17-alpine AS build

WORKDIR /app

# Copy only the Maven descriptor first for dependency caching
COPY Mercado_Libre_Mutantes-main/pom.xml ./
RUN mvn dependency:go-offline -B

# Copy sources and build (skip tests for faster image build)
COPY Mercado_Libre_Mutantes-main/src ./src
RUN mvn clean package -DskipTests -DskipITs

# Runtime stage with a lightweight JRE
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app

# Render sets PORT; app reads it from application.properties
EXPOSE 8080

# Copy the built jar from the previous stage
COPY --from=build /app/target/*.jar ./app.jar

# Start the application
ENTRYPOINT ["java", "-jar", "./app.jar"]
