pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            agent { docker { image 'node:20-alpine' } }
            steps {
                dir('services/service-a') {
                    sh 'npm ci || npm install'
                }
            }
        }

        stage('Unit Tests') {
            agent { docker { image 'node:20-alpine' } }
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