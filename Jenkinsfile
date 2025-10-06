pipeline {
    agent any

    tools {
        nodejs 'Node 20'
    }

    options {
        skipDefaultCheckout true
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/erdemirbass/microservices-ci-cd.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                dir('services/service-a') {
                    sh 'npm ci || npm install'
                }
            }
        }

        stage('Unit Tests') {
            steps {
                dir('services/service-a') {
                    sh 'npm test'
                }
            }
        }

        stage('Docker Build & Push') {
            steps {
                echo 'TODO: Docker build step will go here'
            }
        }

        stage('Smoke Tests') {
            steps {
                echo 'TODO: Smoke tests will go here'
            }
        }

        stage('Manual Approval') {
            steps {
                input message: 'Approve deployment?'
            }
        }

        stage('Deploy') {
            steps {
                echo 'TODO: Deployment step will go here'
            }
        }
    }
}