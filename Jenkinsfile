pipeline {
    agent any
   
    environment {
        DOCKERHUB_CREDENTIALS = credentials('hub1');
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
                    // Đăng nhập vào Docker Hub
                    docker.withRegistry('', DOCKERHUB_CREDENTIALS) {
                        // Kéo hình ảnh từ Docker Hub
                        sh 'docker pull jaytruong/demo:app-demo'
                    }
                }
                // This step should not normally be used in your script. Consult the inline help for details.
                    // withDockerRegistry(credentialsId: 'hub1') {
                    //     // some block
                    // }
            }
        }
    }
}
