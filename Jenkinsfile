pipeline
{
    agent any

    stages
    {
        stage('git clone')
        {
            steps
            {
                git 'https://github.com/chandanchandu1/hello-world.git'
            }
        }

        stage('Build')
        {
            steps
            {
                sh 'mvn clean install'
            }
        }
    }
}