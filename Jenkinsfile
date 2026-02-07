pipeline {
    agent {
        docker {
            image 'maven:3.9.3-openjdk-17'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
