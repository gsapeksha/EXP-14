pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'cd calculator && mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'cd calculator && mvn test'
            }
        }
    }

    post {
        always {
            junit 'calculator/target/surefire-reports/*.xml'
        }
    }
}
