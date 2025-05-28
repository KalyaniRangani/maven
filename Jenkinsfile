@Library('sharedlibrary')_

pipeline
{
    agent any
    stages
    {
        stage('download_sub')
        {
            steps
            {
                script
                {
                    cicd.contdown("maven")
                }
            }
        }
        stage('build_sub')
        {
            steps
            {
                script
                {
                    cicd.contbuild()
                }
            }
        }

    }
}





