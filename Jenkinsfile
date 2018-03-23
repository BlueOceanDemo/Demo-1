pipeline {
    agent { docker "java" }
    stages {
        stage("build") {
            steps {
                sh 'uname -a'
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
