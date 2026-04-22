pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('calculator') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage('Test') {
            steps {
                dir('calculator') {
                    bat 'mvn test'
                }
            }
        }
    }

    post {
        always {
            junit 'calculator/target/surefire-reports/*.xml'
        }
    }
}
