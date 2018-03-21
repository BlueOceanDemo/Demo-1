pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
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
                sh 'echo "This is coming from Jenkins File"' 
            }
        }
        stage('Test-2') {
            steps {
                sh 'echo "This is coming from Dev Branch"'
            }
        }

    }
}
