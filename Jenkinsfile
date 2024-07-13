pipeline {
    agent any 
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
        stage('Push docker Hub') {
             steps {
                 // This step should not  normal l y be used in your script . Consult the inline help for details.
                withDockerRegistry(credentialsId: 'dockerhub' , url: '') {
                // sh label: '' ,script: 'docker pull jaytruong/demo:app-demo'
                sh label: '' ,script :'docker run -d ubuntu sleep infinity '
                }
             }
         }
     }
}
   