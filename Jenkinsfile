pipeline {
    agent any 
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
        stage('Push docker Hub') {
            // This step should not normally be  used in your script. Consult the inline help for details.
           steps {
             withDockerRegistry(credentialsId: 'testhub',url:'') {
                // some block
                sh 'docker --version'
            }
           }
     }
}
}
   