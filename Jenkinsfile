pipeline {
    agent any
   
    environment {
        DOCKERHUB_CREDENTIALS = credentials('hubdocker')
    }
   
    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
         stage('Pull Docker Image') {
            steps {
                script {
                    // Pull image từ Docker Hub
                    docker.image('nginx').pull()
                }
            }
        }
    }
}