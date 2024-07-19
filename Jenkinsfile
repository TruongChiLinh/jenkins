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
                    def dockerVersion = sh(script: 'docker --version', returnStdout: true).trim()
                    echo "Docker version: ${dockerVersion}"
                }
            }
        }
        stage('Pull Docker Image') {
            steps {
                script {
                    // Pull image từ Docker Hu b
                    sh 'docker --version'
                     sh 'docker pull jaytruong/demo:app-demo'
                }
            }
        }
    }
}
