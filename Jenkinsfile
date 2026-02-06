pipeline {
    agent {
        docker {
            image 'maven:3.9.3-openjdk-17' // image officielle Maven + JDK
            args '-v /root/.m2:/root/.m2'  // réutilise le cache Maven
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
                sh 'mvn clean install'  // build Maven
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // unit tests
            }
        }

        stage('Success') {
            steps {
                echo 'Build and test completed successfully!'
            }
        }
    }
}
