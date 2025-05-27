pipeline
{
    agent any
    stages
    {
        stage('continousdownload')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/maven.git'
            }
        }
        stage('continousbuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('continousdeployment')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/Declarativepipeline1/webapp/target/webapp.war ubuntu@172.31.13.212:/var/lib/tomcat10/webapps/mytestapp.war'
            }
        }
        stage('continoustesting')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/Declarativepipeline1/testing.jar'
                
            }
        }
        stage('continousdelivery')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/Declarativepipeline1/webapp/target/webapp.war ubuntu@172.31.2.210:/var/lib/tomcat10/webapps/myprodapp.war'
            }
        }
        
    }
}
