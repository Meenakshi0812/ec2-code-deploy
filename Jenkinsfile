pipeline {
  agent any

  stages {
    stage('Deploy') {
      steps {
        sshagent(credentials: ['jenkins-private-key']) {
          sh '''
            ssh -o StrictHostKeyChecking=no ubuntu@44.204.54.247 "cd /home/ubuntu && git clone https://github.com/Meenakshi0812/new-jenkins-ec2-zip-html.git"
            ssh -o StrictHostKeyChecking=no ubuntu@44.204.54.247 "sudo cp -r /home/ubuntu/new-jenkins-ec2-zip-html/. /var/www/html/"
          '''
        }
      }
    }
  }
}
