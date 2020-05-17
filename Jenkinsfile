pipeline {
 agent any;
 
 stages {
  stage('Installing tomcat') {
  steps {
  sh 'ansible-playbook /opt/jenkins_tomcat/site.yml'
  }
  }

  stage('Deploying WAR') {
 
  steps {
  sh 'wget http://54.91.129.45:8081/nexus/content/repositories/releases/in/javahome/simple-app/1.0/simple-app-1.0.war -P /opt/jenkins_tomcat/'
  
  sh 'ansible-playbook /opt/jenkins_tomcat/deplyoment.yml '
  
  }
  }
 }

}
