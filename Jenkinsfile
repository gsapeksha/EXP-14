pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'dir'
                bat 'mvn -f Calculator/pom.xml clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn -f Calculator/pom.xml test'
            }
        }
    }

    post {
        always {
            junit 'Calculator/target/surefire-reports/*.xml'
        }
    }
}
