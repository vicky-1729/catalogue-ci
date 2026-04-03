pipeline{
    agent { 
        label 'TEST-NODE'
    }

    environment{
        appVersion = ''
    }

    stages{
        stage('Testing') {
            steps{
                script {
                    def packageJson = readJSON file: 'package.json'
                    appVersion = packageJson.version
                    echo "${appVersion}"
                }
            }
        }
    }
}