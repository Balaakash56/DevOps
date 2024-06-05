README.md
# DevOps Java Hello World Project

This repository contains a simple "Hello, World!" Java application, configured to be built with Maven, Docker, and Jenkins.

## Project Structure
├── src/ main/java/com/ example/ └──> HelloWorld.java ├──> pom.xml  ├──> Jenkinsfile |──> Dockerfile.

## Prerequisites

- Java 8
- Maven
- Docker
- Jenkins

## Setting Up the Project

1. Clone the Repository

sh
git clone https://github.com/Balaakash56/DevOps.git
cd DevOps

2. Build the Project with Maven
sh
Copy code
mvn clean package
3. Run the Java Application

sh
Copy code
java -cp target/helloworld-1.0-SNAPSHOT.jar com.example.HelloWorld
Docker Instructions
Build the Docker Image

sh
Copy code
docker build -t helloworld-java .
Run the Docker Container

sh
Copy code
docker run --rm helloworld-java

Jenkins Pipeline Configuration
This project includes a Jenkinsfile that defines a pipeline for building, testing, and deploying the application using Jenkins.

Jenkinsfile Stages
Checkout: Fetches the code from the repository.
Build: Compiles the Java application using Maven.
Test: Runs tests using Maven.
Build Docker Image: Builds a Docker image for the application.
Run Docker Container: Runs the Docker container to execute the application.

Post Steps:
Archives build artifacts.
Publishes test results.
Cleans up Docker images.
Setting Up Jenkins

Install Jenkins: Follow the instructions on the Jenkins website to install Jenkins.

Configure Maven: Ensure Maven is installed and configured in Jenkins (referred to as 'M3' in the Jenkinsfile).

Configure Docker: Make sure the Jenkins user has the necessary permissions to run Docker commands.

Create a Pipeline Job:
Go to Jenkins Dashboard.
Click on "New Item".

Select "Pipeline" and name it appropriately.
In the "Pipeline" section, select "Pipeline script from SCM".

Choose "Git" and provide the repository URL: https://github.com/Balaakash56/DevOps.git.
Specify the branch name, making sure it is correct (e.g., */master).

Troubleshooting

Git Branch Fetch Error

If you encounter an error like Couldn't find any revision to build. Verify the repository and branch configuration for this job.:

Ensure that the branch name is correctly specified in the Jenkins job configuration.

Go to your Jenkins job configuration.

Under the "Source Code Management" section, verify the "Branch Specifier" is set to the correct branch (e.g., */master).
Save and retry the build.
