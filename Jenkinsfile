pipeline {
    agent { docker "java" }
    stages {
        stage("build") {
            steps {
                sh 'uname -a'
            }
            steps {
                sh 'mvn clean install -Dmaven.test.failure.ignore=true'
        }
    }
    post {
        always {
            archive "target/**/*"
            junit 'target/surefire-reports/*.xml'
        }
    }
}

