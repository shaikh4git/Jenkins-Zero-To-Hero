# Use a base image with OpenJDK 11 installed
FROM adoptopenjdk/openjdk11:jre-11.0.11_9-alpine

# Install Maven and procps (for the top command)
RUN apk update && \
    apk add --no-cache maven procps

# Set the working directory
WORKDIR /opt/app

# Copy the application JAR file to the working directory
ARG artifact=target/spring-boot-web.jar
COPY ${artifact} app.jar

# Run the application
ENTRYPOINT ["java", "-jar", "app.jar"]

# Keep the container running
CMD ["tail", "-f", "/dev/null"]
