# GitHub Workflows for Java Projects

This repository contains GitHub workflows designed to automate the build, release, and deployment of Java-based projects, specifically for GCP Artifact Registry and Docker.

## Table of Contents

- [Available Workflows](#available-workflows)
- [Usage Instructions](#usage-instructions)
    - [Build and Deploy Microservice](#build-and-deploy-microservice)
    - [Build and Release with Maven/Gradle](#build-and-release-with-mavengradle)
- [Contribution & Support](#contribution--support)
  
## Available Workflows

The following workflows are available:

1. Build and Deploy Microservice
   - File: `gradle.gcp-artifact-registry.deploy-microservice.yaml`
2. Release final version with Gradle
   - File: `gradle.gcp-artifact-registry.release.final.yaml`
3. Release snapshot version with Gradle
   - File: `gradle.gcp-artifact-registry.release.snapshot.yaml`
4. Release final version with Maven
   - File: `maven.gcp-artifact-registry.release.final.yaml`
5. Release snapshot version with Maven
   - File: `maven.gcp-artifact-registry.release.snapshot.yaml`

## Usage Instructions

### Build and Deploy Microservice

This workflow automates the process of building a microservice, creating a Docker image, and deploying it to a Planton Cloud environment.

#### Inputs:

- `JAVA_DISTRIBUTION` & `JAVA_VERSION`: Specify the Java distribution and version.
- `PLANTON_CLOUD_ARTIFACT_STORE_ID`: The ID of the Artifact Store on Planton Cloud.
- `DOCKER_REPO_HOSTNAME` & `CONTAINER_IMAGE_REPO` & `CONTAINER_IMAGE_TAG`: Information related to the Docker repository.
- `PLANTON_CLOUD_ENVIRONMENT_ID`, `PLANTON_CLOUD_ENVIRONMENT_NAME`, `PLANTON_CLOUD_MICROSERVICE_INSTANCE_VERSION`: Environment-specific details for deployment.

### Build and Release with Maven/Gradle

This workflow automates the process of building a Java project using Maven/Gradle and then releasing it to the GCP Artifact Registry.

#### Inputs:

- `PLANTON_CLOUD_ARTIFACT_STORE_ID`: The ID of the Artifact Store on Planton Cloud.
- `JAVA_PROJECT_ROOT`: Path to the Java project.
- `JAVA_DISTRIBUTION` & `JAVA_VERSION`: Specify the Java distribution and version.
- `JAR_VERSION`: Semantic version of the JAR for the release.

## Contribution & Support

Feel free to contribute to this repository by submitting pull requests. For any issues or support requests, please raise an issue in the repository.

## License

This project is licensed under the [MIT License](LICENSE).
