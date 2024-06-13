pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string(name: 'appVersion', defaultValue: '1.0.0', description: 'What is the application version?')
    }
    environment{
        def appVersion = ''  //variable declaration
        nexusUrl = 'nexus.imvicky.online:8081'
    }
    stages {
        stage('print the version'){
            steps{
                script{
                    echo "Application version: ${params.appversion}"
                }
            }
        }
            

    }    
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success {
            echo 'I will run when pipeline is success'
        }
          failure {
            echo 'I will run when pipeline is failed'
        }
    }
}