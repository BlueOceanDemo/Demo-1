pipeline {
    agent { docker "java" }
    stages {
        stage("build") {
            steps {
                sh 'apt-get update && apt-get install maven'
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
