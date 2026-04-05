pipeline{
    agent { 
        label 'TEST-NODE'
    }

    environment{
        appVersion = ''
    }
    stages{

        stage('Reading the package version') {
            steps{
                script {
                    def packageJson = readJSON file: 'package.json'
                    appVersion = packageJson.version
                    echo "${appVersion}"
                }
            }
        }
        stage('Install Dependices'){
            steps{
                script{
                    sh """
                    npm install
                    """
                }
            }
        }
        stage('input user'){
            input{
                message "Are you ready to connect AWS..?"
                ok "please proceed"
                submitter "vs"

            }
            steps{
                script{
                   sh """
                        aws s3 ls

                    """ 
                }
            }

        }
    }

}