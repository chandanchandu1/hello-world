pipeline
{
    agent any
    environment
    {
        PATH = "/opt/maven/bin:$PATH"
    }

    stages
    {
        stage('git clone')
        {
            steps
            {
                git 'https://github.com/chandanchandu1/hello-world.git'
            }
        }

        stage('Test and Build')
        {
            steps
            {
                sh 'mvn clean install'
            }
        }

        stage('SonarQube: Quality code Analysis')
        {
            steps
            {
                script
                {
                    withSonarQubeEnv(credentialsId: 'Sonar-API-Key') 
                    {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}