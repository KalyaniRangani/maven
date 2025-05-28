@Library('sharedlibrary')_

pipeline
{
    agent any
    stages
    {
        stage('download_master')
        {
            steps
            {
                script
                {
                    cicd.contdown("maven")
                }
            }
        }
        stage('build_master')
        {
            steps
            {
                script
                {
                    cicd.contbuild()
                }
            }
        }
        stage('deploy_master')
        {
            steps
            {
                script
                {
                    cicd.contdeploy("cicdlib","172.31.13.212","test1")
                }
            }
        }
        stage('test_master')
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
        stage('delivery_master')
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





