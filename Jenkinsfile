// pipeline {
//     agent any 
//     stages {
//         stage('Clone') {
//             steps {
//                git 'https://github.com/TruongChiLinh/jenkins.git'
//             }
//         }
//         stage('Push docker Hub') {
//             steps {
//                 // This step should not normally be used in your script. Consult the inline help for details.
//                 withDockerRegistry(credentialsId: 'docker-hub' ,url: '') {
//                // some block
//                sh label:'' ,script: 'docker build -t jaytruong/demo:jenkins .'
//                sh label:'' ,script: 'docker push jaytruong/demo:jenkins'
//              } 
//             }
//         }
//     }
// }
   pipeline {
    agent any 
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
        stage('Build and Push Docker Image') {
            steps {
                script {
                    def dockerImage = 'jaytruong/demo:jenkins'
                    
                    // Build Docker image
                    sh "docker build -t ${dockerImage} ."
                    
                    // Push Docker image (assuming Docker is configured to push to the default registry)
                    sh "docker push ${dockerImage}"
                }
            }
        }
    }
}
