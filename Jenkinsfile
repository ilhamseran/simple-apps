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
                -Dsonar.host.url=http://172.23.1.1:9000 \
                -Dsonar.login=sqp_acc0bad0193430e8f57f9c75c18bbbe1b189631e
              '''
            }
        }

        stage('Build Image') {
            steps {
              sh '''
              docker compose build
              '''
            }
        }

        stage('Push Image') {
            steps {
              sh'''
              docker compose push
              '''
            }
        }

        stage('Deploy Apps') {
            steps {
              sh'''
              docker compose up -d
              '''
            }
        }
    }
}
