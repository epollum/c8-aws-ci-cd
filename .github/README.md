# Camunda 8 CI/CD Example with AWS
This repository contains a working example of a process application. This process application is also found [here in our camunda-8-examples repository](https://github.com/camunda-community-hub/camunda-8-examples/tree/main/payment-example-process-application). For information on how this process is built, please refer to the linked repository.

What this repository focuses on is creating a comprehensive CI/CD pipline using github actions and AWS. This pipeline includes:

* Unit Tests
* Process Tests
* Integration Tests
* Deployment of bpmn,dmn, and Camunda Form resources to a Camunda Cluster
* Deployment of job workers to an AWS EKS cluster

## Repository Layout
In this repository you'll find several folders containing the resources needed to implement this CI/CD.

| Folder | Description                                                                |
|--------|----------------------------------------------------------------------------|
| .github | contains github actions workflows                                          |
| docker | contains Dockerfile for building a docker image of the process application |
| kube | contains kubernetes manifests                                              |
| src   | contains the process application                                           |