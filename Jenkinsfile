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
       
    }
    
}
