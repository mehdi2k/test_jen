pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/mehdi2k/test_jen'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'  // This builds your Maven project
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // This runs your unit tests
            }
        }

        stage('Success') {
            steps {
                echo 'Build and test completed successfully!'
            }
        }
    }
}
