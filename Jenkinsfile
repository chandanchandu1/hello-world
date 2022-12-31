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

        stage('Deploy to tomcat')
        {
            steps
            {
                sshagent(['deploy_user']) 
                {
                    sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.37.107.67:/opt/tomcat/webapps"
                    // scp <src_file> username@IP:<des_path>

                }
            }
        }
    }
}