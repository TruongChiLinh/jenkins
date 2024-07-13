    pipeline {
        agent any 
        stages {
            stage('Clone Code') {
                steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
                }
            }
        
                stage('Pull image') {
                    steps {
                        // This step should not normally be used in your script. Consult the inline help for details.
                        withDockerRegistry(credentialsId: 'hubdocker' ,url:'') {
                           sh 'docker --version' 
                           sh 'docker pull nginx'
                        }
                    }
                }
            
        //     stage('Push docker Hub') {
        //         // This step should not  normally  be  used in  your script. Consult the inline help for details.
        //         steps {
        //             withDockerRegistry(credentialsId: 'testhub' ,url:'') {
        //                 // some block
        //                 sh 'docker --version'
        //                 sh 'docker login'
        //                 sh 'docker pull nginx'
        //             }
        //         }
        //     }
         }
    }
    