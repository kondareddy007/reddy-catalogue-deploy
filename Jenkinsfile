pipeline {
    // agent none
    agent {
        node {
            label 'AGENT'
        }
    }
    
    
    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string (name: 'version', defaultValue: '', description: 'What is artifact version')
        string (name: 'environment', defaultValue: 'dev', description: 'what is environment')
        
    }

    
    stages {
        stage('Print Version'){
           steps{
                sh """
                    echo "version: ${params.version}"
                    echo "environmnet: ${params.environment}"
                """             
            }

        }
        stage('Tesing'){
            steps{
                echo "Testing stage level testing"
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploy the code stage level deploy'
            }
        }
    }

    post {
        always {
            echo 'it will always say hello again'
            deleteDir()
        }
        failure {
            echo " it will throw error message when build is failed"
        }
        success {
            echo "it will display when build when build is success"
        }
    }
}