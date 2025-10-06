pipeline {
    agent any

    environment {
        APP_NAME          = "service-a"
        DOCKER_IMAGE      = "erdemirbass/${APP_NAME}"
        REGISTRY          = "ghcr.io" // TODO: ihtiyacına göre değiştir
        GIT_COMMIT_SHORT  = "${env.GIT_COMMIT.take(7)}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Build stage placeholder: build application"
            }
        }

        stage('Unit Tests') {
            steps {
                echo "Unit tests placeholder: run tests"
            }
        }

        stage('Docker Build & Push') {
            steps {
                echo "Docker build & push placeholder"
            }
        }

        stage('Blue/Green Deploy') {
            steps {
                echo "Blue/Green deploy placeholder"
                sh 'bash scripts/deploy_blue_green.sh'
            }
        }

        stage('Smoke Tests') {
            steps {
                echo "Smoke tests placeholder"
                sh 'bash scripts/run_smoke_tests.sh'
            }
        }

        stage('Manual Approval') {
            steps {
                script {
                    input message: "Yeni sürüm onaylandı mı?"
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline tamamlandı."
        }
        failure {
            echo "Pipeline failed. TODO: Rollback / Notification logic"
        }
    }
}