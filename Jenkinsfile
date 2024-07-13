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
         stage('Pull image') {
                    steps {
                        // This step should not normally be used in your script. Consult the inline help for details.
                       // This step should not normally be used in your script. Consult the inline help for details.
                        withDockerRegistry(credentialsId: 'hubdocker' ,url:'') {
                            sh 'docker pull jaytruong/demo:app-demo '
                        }
                    }
                }
        
    }
}