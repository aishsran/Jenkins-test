pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'C:\\Users\\Hp\\Desktop\\Lead\\Jenkins'
        TESTING_ENVIRONMENT = 'staging'
        PRODUCTION_ENVIRONMENT = 'Aish-Production'
    }

    stages {

        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts"
            }
        }

        stage('Test') {
            steps {
                echo "Unit Tests"
                echo "Integration Tests"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy the application to a ${env.TESTING_ENVIRONMENT} environment "
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep time: 10, unit: 'SECONDS'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to the ${env.PRODUCTION_ENVIRONMENT} environment"
            }
        }
    }

        stage('New Addition - Trigger Integration') {
            steps {
                echo "Auto Trigger Integration is Successfull"
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
