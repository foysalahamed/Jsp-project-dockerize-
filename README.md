# Jsp-project-dockerize-
# Use an official OpenJDK runtime as a parent image
FROM openjdk:8-jdk-alpine

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the application JAR file into the container
COPY target/*.war app.war

# Make port 8080 available to the world outside this container
EXPOSE 8080

# Run the JSP application when the container launches
CMD ["java", "-jar", "app.war"]

docker build -t jsp-app .

docker run -p 8080:8080 jsp-app


Access the Application: Open a web browser and navigate to http://localhost:8080 to access your JSP application running inside the Docker container.Make sure your JSP application is packaged as a WAR file (Web Application Archive) before building the Docker image. You can build the WAR file using tools like Maven or Gradle.Also, ensure your JSP application is configured to run on port 8080 or update the Dockerfile accordingly if it's configured differently. Additionally, if your JSP application requires a database or any other services, you'll need to configure and link them properly in your Docker setup.

