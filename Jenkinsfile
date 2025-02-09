pipeline {
    agent {
        docker {
            image 'maven:3.8-jdk-11'  // This specifies the Docker image with Maven pre-installed
            label 'docker'  // Optional: If you have specific agents labeled, you can add this
        }
    }
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
