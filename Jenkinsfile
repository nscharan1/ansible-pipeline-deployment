pipeline {
 agent any;

 stages {
  stage('Installing the tomcat') {
            steps {
                echo '> Deploying the application'
                ansiblePlaybook(
                    inventory: '/opt/jenkins_tomcat/inventory',
                    playbook: '/opt/jenkins_tomcat/site.yml'
                )
            }
        }

  stage('Deploying WAR') {
   steps {
   sh 'wget http://3.84.218.206:8081/nexus/content/repositories/releases/in/javahome/simple-app/1.0/simple-app-1.0.war'
   sh 'ansible-playbook -i /opt/jenkins_tomcat/inventory /opt/jenkins_tomcat/deployment'
  
  }
  }
 }
}
