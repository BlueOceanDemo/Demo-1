pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000'
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
                sh 'echo "This is Test Stage"'
            }
        }
        stage('Deliver for development') {
            when {
                branch 'dev-1' 
            }
            steps {
                sh 'echo "Step-1"'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo "dev-1 branch success"'
            }
        }
        stage('Deploy for production') {
            when {
                branch 'master'  
            }
            steps {
                sh 'echo "step-2"'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo "master done"'
            }
        }
    }
}
