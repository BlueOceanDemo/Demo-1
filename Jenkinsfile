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
        }
        stage('Deliver for development') {
            when {
                branch 'dev-1' 
            }
            steps {
                sh 'echo "This is from dev-1"'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo "Success"'
            }
        }
        stage('Deploy for production') {
            when {
                branch 'master'  
            }
            steps {
                sh 'This is from Master'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo "Master Branch"'
            }
        }

    }
}
