pipeline {
    agent any

    environment {
        SSH_USER = 'vps1'
        SSH_HOST = '192.168.254.115'
        SSH_PASSWORD = '1234' // Sử dụng Jenkins credentials để bảo mật mật khẩu
    }
    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }
        stage('Test Docker') {
            steps {
                script {
                    // Kiểm tra phiên bản Docker
                    def dockerVersion = sh(script: 'docker --version', returnStdout: true).trim()
                    echo "Docker version: ${dockerVersion}"
                }
            }
        }
        stage('Pull Docker Image') {
            steps {
                script {
                    // Pull image từ Docker Hu b
                    sh 'docker --version'
                     sh 'docker pull jaytruong/demo:app-demo'
                }
            }
        }
         stages {
        stage('Deploy') {
            steps {
                script {
                    sh """
                    sshpass -p '${SSH_PASSWORD}' ssh ${SSH_USER}@${SSH_HOST} << 'EOF'
                        echo "Connected to remote server"
                        # Thực hiện các lệnh trên máy chủ từ xa
                        // cd /path/to/remote/directory
                        // ./deploy.sh
                    EOF
                    """
                }
            }
        }
         }
            }
}
