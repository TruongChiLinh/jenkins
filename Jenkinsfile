pipeline {
    agent any
    environment {
 
    }
    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                // script {
                //     docker.withRegistry('', DOCKERHUB_CREDENTIALS) {
                //         sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                //     }
                // }
                sh 'docker login'
            }
        }
        stage('Pull Docker Image') {
            steps {
                sh 'docker pull nginx'
            }
        }
        // stage('Build Docker Image') {
        //     steps {
        //         sh 'docker build -t your_dockerhub_username/your_image_name:latest .'
        //     }
        // }
        // stage('Push Docker Image') {
        //     steps {
        //         script {
        //             docker.withRegistry('', DOCKERHUB_CREDENTIALS) {
        //                 sh 'docker push your_dockerhub_username/your_image_name:latest'
        //             }
        //         }
        //     }
        // }
    }
}
