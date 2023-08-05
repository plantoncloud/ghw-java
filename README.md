# GitHub Workflow: Build and Release Java JAR

This repository provides a GitHub Workflow that automates the process of building a Java Microservice and releasing the JAR file to a Maven repository using Gradle and Planton Cloud.

The workflow performs the following steps:

1. **Checkout Code:** Fetches your application's codebase from the repository.

2. **Install Planton CLI:** Installs the Planton Command Line Interface (CLI), a key tool used in subsequent steps.

3. **Verify Planton CLI Installation:** Checks the installed Planton CLI version to verify the successful installation.

4. **Login to Planton Cloud:** Authenticates your session using the provided Planton Cloud credentials.

5. **Setup Java:** Sets up the Java environment necessary for building the application using Gradle. It uses OpenJDK 17 and caches Gradle dependencies.

6. **Setup Google Application Credentials:** Fetches the Artifact Store key from Planton Cloud and sets it up as the Google Application Credentials.

7. **Build & Publish with Gradle:** Builds your application and publishes the resulting JAR file to a Maven repository. It utilizes the version you pass in as an input to the workflow.

## Usage

To make use of this workflow, you need to include it in your GitHub Actions. The workflow can be triggered on a `workflow_call`.

```yaml
on:
  workflow_call:
```

### Secrets and Inputs

The workflow requires the following secrets and inputs to be passed when calling the workflow:

#### Secrets

- `PLANTON_CLOUD_CLIENT_ID`: Your Planton Cloud Client ID.
- `PLANTON_CLOUD_CLIENT_SECRET`: Your Planton Cloud Client Secret.

#### Inputs

- `PLANTON_CLOUD_ARTIFACT_STORE_ID`: The ID of the Artifact Store on Planton Cloud.
- `PLANTON_CLOUD_MICROSERVICE_INSTANCE_VERSION`: The version of the Microservice Instance.
- `JAR_VERSION`: The semantic version of the JAR to be used for the release.
- `JAVA_PROJECT_ROOT`: The path of the Java project relative to the root of the repository. Defaults to the root of the repository if not provided.

## Contributing

If you have suggestions for how this GitHub Action could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

## License

This project is licensed under the [MIT License](LICENSE).
