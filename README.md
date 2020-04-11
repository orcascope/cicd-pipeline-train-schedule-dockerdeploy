# cicd-pipeline-train-schedule-dockerdeploy

This is a simple train schedule app written using nodejs. It is intended to be used as a sample application for a series of hands-on learning activities.

## Running the app

You need a Java JDK 7 or later to run the build. You can run the build like this:

    ./gradlew build

You can run the app with:

    ./gradlew npm_start

Once it is running, you can access it in a browser at http://localhost:8080

Additional Information and Resources
Your team is transitioning from a traditional static deployment model to using containers. They hope to eventually implement container orchestration, but right now they want to take the step of running the train-schedule app in production as a Docker container. The team also wants to maintain an automated CI/CD process through this transition. A Dockerfile has already been created for the app which can be used to build Docker images for it, and a production server has been set up with Docker installed.

The team has asked you to modify the Jenkins Pipeline and configure Jenkins so that the Docker image can be built and deployed as part of the Jenkins CD Pipeline. You will need to do the following:

Configure Jenkins credentials for the production server.
Configure Jenkins credentials for the Docker image registry (Docker Hub).
Configure a global property in Jenkins to store the production server IP.
Create a multibranch pipeline project in Jenkins called train-schedule.
Configure the Jenkins project to pull from your fork of the source code.
Stages to the Jenkins Pipeline (Jenkinsfile) to do the following:
Build a Docker image with the code inside it.
Push the image to Docker Hub.
Deploy the new image to production: stop and remove any older containers, pull and run the newly built image.
You will need a Docker hub account in order to use Docker Hub as an image registry. You will need to enter your credentials into the lab environment Jenkins instance, so feel free to create a fresh Docker Hub account and cancel it after you are done.

You will need to create a personal fork of the source code here: https://github.com/linuxacademy/cicd-pipeline-train-schedule-dockerdeploy

Check out the Jenkinsfile on the example-solution branch for an example of how this pipeline can be implemented. If you use that code, however, be sure to change all references to the willbla/train-schedule Docker image name to a name that is unique to your Docker Hub account, such as <your Docker Hub username>/train-schedule.
