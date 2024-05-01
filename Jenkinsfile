pipeline {
    agent any
// vAN aN duONG
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
            post {
            success {
            // Send email notification on successful pipeline test
            emailext(to: "andv2013@gmail.com",
            subject: "Successful test",
            body: "The pipleline has successful test!",
            attachLog: true)
            
            }
            failure {
            // Send email notification on pipeline failure test
            emailext(to: "andv2013@gmail.com",
            subject: "Failed pipeline test",
            body: "The pipleline has failed test. PLease check!",
            attachLog: true)
        }
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
            post {
            success {
            // Send email notification on successful pipeline test
            emailext(to: "andv2013@gmail.com",
            subject: "Successful security scan",
            body: "The pipleline has successful security scan!",
            attachLog: true)
            
            }
            failure {
            // Send email notification on pipeline failure test
            emailext(to: "andv2013@gmail.com",
            subject: "Failed pipeline security scan",
            body: "The pipleline has failed security scan. PLease check!",
            attachLog: true)
        }
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
