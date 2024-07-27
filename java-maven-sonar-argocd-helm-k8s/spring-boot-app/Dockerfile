# Use a base image with OpenJDK 11 installed
FROM openjdk:11-jre-slim

# Install Maven and procps (for the top command)
RUN apt-get update && \
    apt-get install -y maven procps && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /opt/app

# Copy the application JAR file to the working directory
ARG artifact=target/spring-boot-web.jar
COPY ${artifact} app.jar

# Run the application
ENTRYPOINT ["java", "-jar", "app.jar"]

#
