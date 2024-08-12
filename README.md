HelloWorld Servlet Example with Docker
This project demonstrates a simple HelloWorld Servlet application, complete with a corresponding Dockerfile for containerization.

Prerequisites
Maven: Ensure Maven is installed to build the project.
Docker: Docker is required to build and run the container.
Building the Project
First, use Maven to build the project and generate the .war file:


mvn clean package
The compiled artifact will be created in the target directory.

Creating the Docker Image
Once the project is built, you can create a Docker image using the following command:


docker build -t mavenbuild .
This command will build the Docker image and tag it as mavenbuild.

Verifying the Docker Image
After the build completes, you can verify that the Docker image was created successfully by listing all Docker images:


docker images
You should see mavenbuild listed among your Docker images.

Running the Docker Container
To run the Docker container using the image you just created, use the following command:


docker run -d -p 8080:8080 --name dockercontainer mavenbuild
The -d flag runs the container in detached mode (in the background).
The -p 8080:8080 option maps port 8080 on your local machine to port 8080 in the container.
The --name dockercontainer assigns the name dockercontainer to the running container.
mavenbuild is the name of the Docker image you built earlier.
Once the container is running, you can access the HelloWorld servlet by navigating to "localhost:8080" in your web browser.
