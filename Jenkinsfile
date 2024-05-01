pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven."
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests and integration tests."
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Analyzing the code with ESLint."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing a security scan using JFrog."
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying to a staging server on AWS EC2."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging server."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying to a production server on AWS EC2."
            }
        }
    }

    post {
        success {
            // Send email notification on successful pipeline completion
            emailext(to: "andv2013@gmail.com",
            subject: "Successful pipeline",
            body: "The pipleline has successful!",
            attachLog: true)
            
        }
        failure {
            // Send email notification on pipeline failure
            emailext(to: "andv2013@gmail.com",
            subject: "Failed pipeline",
            body: "The pipleline has failed. PLease check!",
            attachLog: true)
        }
    }
}
