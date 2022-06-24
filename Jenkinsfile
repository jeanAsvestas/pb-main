pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim Docker image'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }        
    }
}