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
                echo 'Building the project using Maven'
                echo 'Tool: Apache Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests'
                echo 'Tools: JUnit, TestNG'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing static code analysis using SonarQube'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scan using OWASP Dependency-Check'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to the staging server'
                echo 'Method: SCP or remote PowerShell/SSH'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests in staging environment'
                echo 'Tool: Postman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to the production server'
                echo 'Method: SCP or remote PowerShell/SSH'
            }
        }
    }
    
    post {
        success {
            echo "Pipeline Executed Successfully!!"
            emailext(
                to: "aishsinghsran@gmail.com",
                subject: "Build Status Report",
                body: "Build Was Successful!",
                attachLog: true
            )
        }
        failure {
            echo "Pipeline Execution Failed."
            emailext(
                to: "aishsinghsran@gmail.com",
                subject: "Build Status Report",
                body: "Build Was not Successful, Please check the attached Logs.",
                attachLog: true
            )
        }    
    }    
}
