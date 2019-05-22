pipeline
{
    agent any
    stages
    {
        stage('Compile Stage')
        {
            steps
            {
                withMaven(maven :'MVN')
                {
                    sh 'mvn clean install'
                }
            }
        }
        stage('Testing Stage')
        {
            steps
            {
                withMaven(maven :'MVN')
                {
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy')
        {
            steps
            {
               sh label: '', script: 'sh sshpass -p "suman148" "scp -r /root/.jenkins/workspace/code-pipeline/in28minutes-web-servlet-jsp/target/*.war ankitr@172.31.35.75:/opt/apache-tomcat-7.0.94/webapps"'
            }    
        }
        
    }
}
