pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
        stage('Test Docker') {
            steps {
                script {
                    // Kiểm tra phiên bản Docker
                    sh 'docker --version'
                    echo "Docker version: $(docker --version)"
                }
            }
        }
        stage('Pull Docker Image') {
            steps {
                script {
                    // Pull image từ Docker Hub
                    sh 'docker pull nginx:latest'
                }
            }
        }
    }
}
