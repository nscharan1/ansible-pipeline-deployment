pipeline {
 agent any;
 
 stages {
  stage('Deploy') {
            steps {
                echo '> Deploying the application ...'
                sh 'sudo ansible-playbook /opt/jenkins_tomcat/site.yml -i /opt/jenkins_tomcat/inventory'
            }
        }


 }

}
