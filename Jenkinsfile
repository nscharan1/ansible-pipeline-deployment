pipeline {
 agent any;
 
 stages {
  stage('Deploy') {
            steps {
                echo '> Deploying the application ...'
                ansiblePlaybook(
                    vaultCredentialsId: 'AnsibleVault',
                    inventory: '/opt/jenkins_tomcat/inventory',
                    playbook: '/opt/jenkins_tomcat/site.yml'
                )
            }
        }
  
  stage('Installing tomcat') {
  steps {
  ansiblePlaybook(credentialsId: 'pri', inventory: '/opt/jenkins_tomcat/', playbook: 'site.yml') 
  
  }
  }

  stage('Deploying WAR') {
 
  steps {
  sh 'wget http://3.84.218.206:8081/nexus/content/repositories/releases/in/javahome/simple-app/1.0/simple-app-1.0.war'
  
  sh 'ansible-playbook -i /opt/jenkins_tomcat/inventory /opt/jenkins_tomcat/deplyoment.yml '
  
  }
  }
 }

}
