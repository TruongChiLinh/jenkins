pipeline {
    agent any

    environment {
        SSH_USER = 'vps1'
        SSH_HOST = '192.168.254.115'
        SSH_PASSWORD = credentials('ssh-password') // Sử dụng Jenkins credentials
    }

    stages {
        stage('Install sshpass') {
            steps {
                script {
                    // Cài đặt sshpass mà không cần sử dụng sudo
                    sh 'apt-get update && apt-get install -y sshpass'
                }
            }
        }
     stages {
        stage('Test Credentials') {
            steps {
                script {
                    echo "Mật khẩu SSH: ${SSH_PASSWORD}" // In mật khẩu ra để kiểm tra
                }
            }
        }
    }
        stage('Clone Code') {
            steps {
                git 'https://github.com/TruongChiLinh/jenkins.git'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh """
                    sshpass -p '${SSH_PASSWORD}' ssh ${SSH_USER}@${SSH_HOST} << 'EOF'
                        echo "Đã kết nối đến máy chủ từ xa"
                        # Thực hiện các lệnh trên máy chủ từ xa
                        # cd /path/to/remote/directory
                        # ./deploy.sh
                    EOF
                    """
                }
            }
        }
    }
}
