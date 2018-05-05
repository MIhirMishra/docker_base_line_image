In this project, we use AWS CodeBuild to build both the Java application (using Maven) and
its Docker image. The Docker image is a Java environment that launches the Spring Boot application. 
Once the Docker image is built, we use AWS CodeBuild^ to push the Docker image to 
EC2 Container Registry (ECR).

To avoid installing the Java SDK and Maven tool each time we build our project, 
we can create a custom build environment to create Docker image which is pre-installed with all the
dependencies. If we end up have many services this docker image may work as baseline image
for all of the services and as a result all of the services would have same version of common
libraries like java sdk, maven and aws cli.

^AWS CodeBuild is a fully managed build service that compiles source code, runs tests, 
and produces software packages that are ready to deploy.

Any change in this repo will trigger the built of new docker image which is pushed to ECR.


