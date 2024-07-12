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
                 // This step should not normall y be used in your script . Consult the inline help for details.
                withDockerRegistry(credentialsId: 'dockerhub' , url: '') {
                sh label: '' ,script: 'docker pull nginx'
}
             }
         }
     }
}
   