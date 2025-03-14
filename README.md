XNL Jenkins Pipeline

This repository contains a Jenkins pipeline configuration (Jenkinsfile) for a Java Maven project, integrating SonarQube for code analysis, JaCoCo for code coverage, and duplication analysis.

Prerequisites

Ensure you have the following tools installed and configured:

Jenkins (with required plugins: Pipeline, Maven Integration, SonarQube Scanner, JaCoCo)

Apache Maven (configured with Jenkins)

SonarQube (running locally or on a server)

Java Development Kit (JDK)

Git

Pipeline Stages

1. Checkout

Clones the source code from the Git repository.

2. Clean Target Folder

Cleans the target directory to remove old compiled files.

3. Test

Runs unit tests using Maven.

Generates code coverage report using JaCoCo.

4. Package

Packages the compiled Java application into a JAR/WAR file.

5. SonarQube Analysis

Runs static code analysis using SonarQube.

Checks for code smells, bugs, vulnerabilities, duplications, and code coverage.

Environment Variables

MAVEN_PATH: Path to the local Maven installation.

SONAR_TOKEN: Credentials for SonarQube authentication (configured in Jenkins).

Configuration

Modify Jenkinsfile to match your local setup:

Update the SonarQube Project Key (sonar.projectKey=xnl).

Set the correct SonarQube URL (sonar.host.url=http://localhost:9000).

Ensure the correct Maven path is set.

Running the Pipeline

Push the project to the Git repository.

Configure a Jenkins job with Pipeline type.

Point Jenkins to the Jenkinsfile in this repository.

Run the pipeline and monitor the logs.

Post-Build Actions

If the pipeline succeeds, a success message is displayed.

If the pipeline fails, check the logs for errors.
