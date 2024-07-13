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
        //  stage('Pull Docker Image') {
        //     steps {
        //         script {
        //             // Pull image từ Docker Hub tu repo
        //             docker.image('nginx').pull()
        //         }
        //     }
        // }
   
    
    
        stage('Test Docker') {
            steps {
                script {
                    def dockerVersion = sh(script: 'docker --version', returnStdout: true).trim()
                    echo "Docker version: ${dockerVersion}"
                }
            }
        }
   
    }
    
}