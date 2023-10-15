pipeline {
    agent {
        node {
            label 'server1-ilham'
        }
    }

    stages {
        stage('Build Apps') {
            steps {
              sh '''cd apps
              npm install
              '''
            }
        }

        stage('Test Apps') {
            steps {
              sh '''cd apps
              cp -r /root/simple-apps/apps/.env . 
              npm test
              '''
            }
        }

        stage('Scanning Sonnar') {
            steps {
              sh '''
              cd apps
              sonar-scanner \
                -Dsonar.projectKey=Simple-Apps \
                -Dsonar.sources=. \
                -Dsonar.host.url=http://10.23.0.11:9000 \
                -Dsonar.login=sqp_acc0bad0193430e8f57f9c75c18bbbe1b189631e
              '''
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
