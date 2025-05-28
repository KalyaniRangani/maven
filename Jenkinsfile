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

    }
}





