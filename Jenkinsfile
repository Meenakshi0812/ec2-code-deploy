pipeline {
  agent any

  stages {
    stage('Deploy') {
      steps {
        sshagent(credentials: ['jenkins-private-key']) {
          sh '''
            ssh ubuntu@54.89.87.196 "cd /home/ubuntu && git clone https://github.com/Meenakshi0812/ec2-code-deploy.git"
            scp -r /home/ubuntu/ec2-code-deploy/index.html ubuntu@54.89.87.196:/var/www/html/
            ssh ubuntu@54.89.87.196 "sudo service apache2 restart"
          '''
        }
      }
    }
  }
}
