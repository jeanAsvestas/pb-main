pipeline {
    agent {
        docker {
            image 'node:16.13.1-alpine'
            args '-p 3000:3000'
        }
    }
    tools{
        nodejs '16.13.1'
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }   
        stage('Test') {
            steps {
                sh './jenkins/script/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }     
    }
}