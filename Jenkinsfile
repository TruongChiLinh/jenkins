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
                // This step should not normally be used in your script. Consult the inline help for details.
                withDockerRegistry(credentialsId: 'dockerhub' ,url: '') {
               // some block
               sh label:'' ,script: 'docker build -t jaytruong/demo:app-test1 .'
               sh label:'' ,script: 'docker push  jaytruong/demo:app-test1'
             } 
            }
        }
    }
}
   