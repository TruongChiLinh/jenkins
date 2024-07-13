pipeline {
    agent any
   
    environment {
        DOCKERHUB_USER = 'jaytruong'
        DOCKERHUB_TOKEN = credentials('hub1')
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
                    // Đăng nhập vào Docker Hub với token
                    docker.withRegistry('https://index.docker.io/v1/', 'DOCKERHUB_TOKEN') {
                        sh "echo $DOCKERHUB_TOKEN_PSW | docker login -u $DOCKERHUB_USER --password-stdin"
                        sh 'docker pull jaytruong/demo:app-demo'
                    }
                }
            }
        }
    }
}
