# Use the specified base image
FROM adoptopenjdk/openjdk11:ubuntu

# Set the argument for the artifact path
ARG artifact=target/spring-boot-web.jar

# Set the working directory
WORKDIR /opt/app

# Install Maven and procps (for the top command)
RUN apt-get update && \
    apt-get install -y maven procps && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Copy the application JAR file to the working directory
COPY ${artifact} app.jar

# Set the entry point for the container
ENTRYPOINT ["java", "-jar", "app.jar"]

