# Use an official Maven image as the base image
FROM maven:3.8.4-openjdk-11 AS builder

# Set the working directory in the container
WORKDIR /app

# Copy the Maven project files to the container
COPY . /app

# Build the project using Maven and package it into a JAR file
RUN mvn clean package

# Use an official OpenJDK image as the base image for the runtime environment
FROM adoptopenjdk:11-jre-hotspot

# Set the working directory in the container
WORKDIR /app

# Copy the JAR file built in the previous stage to the container
COPY --from=builder /app/target/*.jar /app/application.jar

# Expose the port on which the Spring Boot application will run
EXPOSE 9090

# Command to run the Spring Boot application
CMD ["java", "-jar", "application.jar"]

