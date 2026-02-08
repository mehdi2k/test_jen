pipeline {
    agent {
        docker {
            image 'maven:3.9.3-openjdk-17' // image officielle Maven + JDK
            args '-v /root/.m2:/root/.m2'  // réutilise le cache Maven
        }
    }

    stages {

    stage('Diagnostics') {
                steps {
                    sh 'pwd'                          // where are we?
                    sh 'ls -la'                      // what files were checked out?
                    sh 'git status'                  // confirm repo state
                    sh 'java -version'               // JDK is really there?
                    sh 'mvn --version'               // Maven is really there?
                    sh 'mvn help:effective-settings' // show resolved Maven settings
                }
            }

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
