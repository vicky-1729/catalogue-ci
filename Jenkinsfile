// pipeline{
//     agent { 
//         label 'TEST-NODE'
//     }

//     environment{
//         appVersion = ''
//     }
//     stages{

//         stage('Reading the package version') {
//             steps{
//                 script {
//                     def packageJson = readJSON file: 'package.json'
//                     appVersion = packageJson.version
//                     echo "${appVersion}"
//                 }
//             }
//         }
//         stage('Install Dependices'){
//             steps{
//                 script{
//                     sh """
//                     npm install
//                     """
//                 }
//             }
//         }
//         stage('input user'){
//             input{
//                 message "Are you ready to connect AWS..?"
//                 ok "please proceed"
//                 submitter "vs"

//             }
//             steps{
//                 script{
//                    sh """
//                         aws s3 ls

//                     """ 
//                 }
//             }

//         }
//     }

// }


#free style pipeline

pipeline{


    agent {
        label: 'AGENT_1'
    }
    environment{
        env 'TEST'
    }

    options{
        nonConcurrentBuilds
        timer [ ]
    }
   
    stages{

        stage('Build') {
            steps{
                echo "this is build stage only...!"
            }
        }
        
        stage('Deploy'){
            steps{
                script{
                    sh '''
                        npm install
                    '''
                }
            }
        }

        satge('Testing'){
            steps{
                echo "Testing only"
            }
        }
    }
  post{
    success {
       echo " it is success"
    }
    failure{
        echo "it was failure"
    }
    always{{
        echo "it was alwys print "
    }}
  }




}