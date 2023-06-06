pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                script {
                    def timeStamp = new Date().format("yyyyMMdd_HHmmss")
                    def folderName = "code_${timeStamp}"
                    
                    // SSH into EC2 instance and clone the Git repository
                    sshagent(credentials: ['jenkins-private-key']) {
                        sh "ssh ubuntu@54.89.87.196 'cd /home/ubuntu && git clone https://github.com/Meenakshi0812/ec2-code-deploy.git ${folderName}'"
                    }
                }
            }
        }
    }
}
