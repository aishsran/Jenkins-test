pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'C:\\Users\\Hp\\Desktop\\PPI GIT\\Jenkins'
        TESTING_ENVIRONMENT = 'staging'
        PRODUCTION_ENVIRONMENT = 'Aish-Production'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building the project using Maven...'
                echo 'Tool: Apache Maven'
                echo 'Command: mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                echo 'Tools: JUnit, TestNG'
                echo 'Command: mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing static code analysis using SonarQube...'
                echo 'Tool: SonarQube'
                echo 'Command: sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scan using OWASP Dependency-Check...'
                echo 'Tool: OWASP Dependency-Check'
                echo 'Command: dependency-check --project MyApp --scan . --format ALL'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to the staging server...'
                echo 'Server: AWS EC2 (Staging)'
                echo 'Method: SCP or remote PowerShell/SSH'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests in staging environment...'
                echo 'Tool: Postman (via Newman CLI)'
                echo 'Command: newman run tests/staging_collection.json'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to the production server...'
                echo 'Server: AWS EC2 (Production)'
                echo 'Method: SCP or remote PowerShell/SSH'
            }
        }
    }
    
    post {
        success {
            echo "Pipeline Executed Successfully!"
        }
        failure {
            echo "Pipeline Execution Failed."
        }
    }
}
