@Library('sharedlibrary')_

pipeline
{
    agent any
    stages
    {
        stage('continousdownload')
        {
            steps
            {
                script
                {
                    cicd.contdown("maven")
                }
            }
        }
        stage('continousbuild')
        {
            steps
            {
                script
                {
                    cicd.contbuild()
                }
            }
        }
        stage('continousdeploy')
        {
            steps
            {
                script
                {
                    cicd.contdeploy("cicdlib","172.31.13.212","test1")
                }
            }
        }
        stage('continoustest')
        {
            steps
            {
                script
                {
                    cicd.contdown("FunctionalTesting")
                    cicd.conttest("cicdlib")
                }
            }
        }
        stage('continousdelivery')
        {
            steps
            {
                script
                {
                    cicd.contdeploy("cicdlib","172.31.2.210","prod1")
                }
            }
        }
    }
}





