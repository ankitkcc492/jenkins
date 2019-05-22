pipeline {

    agent any
    tools {
        maven 'MVN_3.6.1' 
    }
    stages {
        stage('Compile stage') {
            steps {
                sh "mvn clean install" 
        }
    }

         stage('testing stage') {
             steps {
                sh "mvn test"
        }
    }

        stage('Deploy') {
            steps {       
         sh label: '', script: 'sh sshpass -p "Acl@ankit148" "scp -r /root/.jenkins/workspace/code-pipeline/in28minutes-web-servlet-jsp/target/*.war ankitr@172.31.35.75:/opt/apache-tomcat-8.5.40/webapps/"'
            }
        }

  }
