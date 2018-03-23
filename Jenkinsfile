pipeline {
    agent { docker "java" }
    stages {
        stage("build") {
            steps {
                sh 'apt-get update -y && apt-get install maven -y && mvn clean install -Dmaven.test.failure.ignore=true'
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
