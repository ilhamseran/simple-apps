pipeline {
    agent {
        node {
            label 'server1-ilham'
        }
    }

    stages {
        stage('Build Apps') {
            steps {
              echo "Build Apps"
            }
        }

        stage('Test Apps') {
            steps {
              echo "Test Apps"
            }
        }

        stage('Scanning Sonnar') {
            steps {
              echo "Scanning Sonar"
            }
        }

        stage('Build Image') {
            steps {
              echo "Build Image"
            }
        }

        stage('Push Image') {
            steps {
              echo "Push Image"
            }
        }

        stage('Deploy Apps') {
            steps {
              echo "Deploy Apps"
            }
        }
    }
}
