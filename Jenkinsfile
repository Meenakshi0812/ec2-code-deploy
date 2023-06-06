pipeline {
  agent any

  stages {
    stage('Deploy') {
      steps {
        sshagent(credentials: ['jenkins-private-key']) {
          sh '''
            ssh ubuntu@44.204.54.247 "cd /home/ubuntu && git clone https://github.com/Meenakshi0812/ec2-code-deploy.git"
            ssh ubuntu@44.204.54.247 "sudo cp -r /home/ubuntu/ec2-code-deploy/. /var/www/html/"
          '''
        }
      }
    }
  }
}
