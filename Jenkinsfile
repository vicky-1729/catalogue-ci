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
    }
}