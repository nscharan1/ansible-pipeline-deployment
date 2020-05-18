pipeline {
 agent any;
 
 stages {
  stage('Deploy') {
            steps {
                echo '> Deploying the application ...'
                ansiblePlaybook become: true, installation: 'Ansible', inventory: '/opt/jenkins_tomcat/inventory', playbook: '/opt/jenkins_tomcat/site.yml'
            }
  }


 }

}
