pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim'
            label 'docker-agent'
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