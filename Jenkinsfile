pipeline {
    agent any

    stages {
        stage('Clone from GitHub') {
            steps {
                git 'https://github.com/Blendgashi05/hello-world-docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("blend05/hello-world-docker:latest")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
                        docker.image("blend05/hello-world-docker:latest").push()
                    }
                }
            }
        }
    }
}