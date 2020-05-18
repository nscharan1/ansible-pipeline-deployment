pipeline {
 agent any;
 
 stages {
  stage('Deploy') {
            steps {
                echo '> Deploying the application ...'
                sh 'ansible-playbook /opt/jenkins_tomcat/site.yml -i /opt/jenkins_tomcat/inventory --private-key /opt/jenkins_tomcat/keys/pri'
            }
        }


 }

}
