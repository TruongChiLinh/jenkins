pipeline {
    agent any 
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
    //     stage('Push docker Hub') {
    //         steps {
    //             // This step should not normally be used in your script. Consult the inline help for details.
    //             withDockerRegistry(credentialsId: 'docker-hub' ,url: '') {
    //            // some block//
    //         //    sh label:'' ,script: 'docker build -t jaytruong/demo:jenkins .'
    //              sh label:'' ,script: 'docker pull jaytruong/demo:app-demo'
    //          } 
    //         }
    //     }
    // }
    stage('Pull Docker Image') {
            steps {
                script {
                    // Pull the Docker image from Docker Hub
                    docker.withRegistry('', 'docker-hub') {
                        def imageName = 'jaytruong/demo:app-demo'  // Replace with your Docker image name and tag
                        docker.image(imageName).pull()
                    }
                }
            }
        }
}
}
   