pipeline {
    agent {
        docker {
            reuseNode true
            image 'node:lts-bullseye-slim'
            label 'docker-agent'
            args '-p 3000:3000' 
        }
    }
    environment {
        HOME = "${WORKSPACE}"
        NPM_CONFIG_CACHE = "${WORKSPACE}/.npm"
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}