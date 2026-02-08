pipeline {
    agent any

    environment {
        APP_NAME = "MyApp"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
            }
        }

        stage('Code Quality') {
            steps {
                echo "Running SonarQube analysis"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application v2"
            }
        }
    }

    post {
        success {
            echo "Deployment successful!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
