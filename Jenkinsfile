pipeline {
 agent any;
 
 stages {
  stage('Deploy') {
            steps {
                echo '> Deploying the application ...'
                ansiblePlaybook(
                    disableHostKeyChecking: true
                    inventory: '/opt/jenkins_tomcat/inventory',
                    playbook: '/opt/jenkins_tomcat/site.yml'
                )
            }
        }

  stage('Deploying WAR') {
 
  steps {
  sh 'wget http://34.207.72.161/:8081/nexus/content/repositories/releases/in/javahome/simple-app/1.0/simple-app-1.0.war'
  
  sh 'ansible-playbook -i /opt/jenkins_tomcat/inventory /opt/jenkins_tomcat/deplyoment.yml '
  
  }
  }
 }

}
