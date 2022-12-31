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
                bat 'mvn clean install'
            }
        }
    }
}