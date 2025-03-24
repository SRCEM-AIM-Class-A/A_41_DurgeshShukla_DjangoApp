pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('durgeshshukla09-dockerhub')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIM-Class-A/A_41_DurgeshShukla_DjangoApp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("durgeshshukla09/studentproject:latest")
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://hub.docker.com/repositories/durgeshshukla09', DOCKER_HUB_CREDENTIALS) {
                        docker.image("durgeshshukla09/studentproject:latest").push()
                    }
                }
            }
        }
    }
}