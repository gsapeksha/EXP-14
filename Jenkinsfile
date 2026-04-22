pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('Calculator') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage('Test') {
            steps {
                dir('Calculator') {
                    bat 'mvn test'
                }
            }
        }
    }

    post {
        always {
            junit 'Calculator/target/surefire-reports/*.xml'
        }
    }
}
