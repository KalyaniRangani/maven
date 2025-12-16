pipeline
{
    agent any
    stages
    {
        stage('continous download')
        {
            steps
            {
                script
                {
                   git 'https://github.com/IntelliqDevops/maven12.git'
                }
            }
        }
        stage('continous build')
        {
            steps
            {
                script
                {
                   sh 'mvn package'
                }
            }
        }
        stage('continous deploy')
        {
            steps
            {
                script
                {
                   sh 'scp /var/lib/jenkins/workspace/Declarative/webapp/target/webapp.war ubuntu@172.31.19.199:/var/lib/tomcat10/webapps/testapp2.war'
                }
            }
        }
        stage('continous testing')
        {
            steps
            {
                script
                {
                   git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
                   sh 'java -jar /var/lib/jenkins/workspace/Declarative/testing.jar'
                }
            }
        }
        stage('continous delivery')
        {
            steps
            {
                script
                {
                   sh 'scp /var/lib/jenkins/workspace/Declarative/webapp/target/webapp.war ubuntu@172.31.20.35:/var/lib/tomcat10/webapps/prodapp2.war'
                }
            }
        }
    }
}
