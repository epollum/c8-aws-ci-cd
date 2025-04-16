# Github Action Workflows
This repository contains several Github Action Workflows. You will find a description of eah one below.


## build-and-push-to-aws-yml
This workflow is used to build a Docker image containing the worker jar, and deploy it to AWS ECR and EKS.
It has the following steps:


| Step Name                                | Description                                                                                                                         | Links                                                    |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| Checkout Repository                      | checkout entire repository                                                                                                          |                                                          |
| Set up JDK                               | set up the jdk to use                                                                                                               | https://github.com/actions/setup-java                    |
| Build with Maven                         | build via mvn package. can choose to run tests here or any maven command. copy target folder to docker folder for docker build step |                                                          |
| Configure AWS credentials                | provide AWS credentials to access ECR and EKS                                                                                       | https://github.com/aws-actions/configure-aws-credentials |
| Login to Amazon ECR                      | perform AWS login                                                                                                                   | https://github.com/aws-actions/amazon-ecr-login          |
| Build, tag, and push image to Amazon ECR | switch to docker folder. build the docker image from dockerfile, tag with the git sha, and push to ECR.                             |                                                          |
| Update kube config                       | set the kubectl context to the desired EKS cluster                                                                                  |                                                          |
| Deploy to EKS                            | use kubectl apply to update worker deployment with latest image                                                                     |                                                          |
