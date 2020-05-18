pipeline {
 agent any;
 
 stages {
  stage('Deploy') {
            steps {
                echo '> Deploying the application ...'
                ansiblePlaybook(
                  inventory: '/opt/jenkins_tomcat/inventory'
                  playbook: '/opt/jenkins_tomcat/site.yml'
                  disableHostKeyChecking: true
                )
            }
  }


 }

}
