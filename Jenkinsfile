pipeline {
    agent { docker "java" }
    stages {
        stage("build") {
            steps {
                sh 'apt-get install maven2 -y'
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
