pipeline {
    agent { docker "java" }
    stages {
        stage("build") {
            steps {
                sh 'apt-get update'
            }
        }
    }
    post {
        always {
            archive "target/**/*"
            junit 'target/surefire-reports/*.xml'
        }
    }
}
