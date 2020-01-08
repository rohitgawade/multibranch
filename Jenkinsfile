pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload')
        {
            steps
            {
            git 'https://github.com/rohitgawade/declarative-pipe.git'
            }
        }
        stage('ContinousBuild')
        {
            steps
            {
               sh label: '', script: 'mvn package'
            }
        }
        stage('continusdeploy')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.36.235:/var/lib/tomcat8/webapps/testapp.war'
            }
        }
        stage('continoustesting')
        {
            steps
            {
            git 'https://github.com/rohitgawade/functionaltesting.git'
            sh label: '', script: 'echo testing pass '
            }
        }
        stage('continusdelivery')
        {
            steps
            {
                 sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.35.125:/var/lib/tomcat8/webapps/prod.war'
            }
        }
    }
    
}
