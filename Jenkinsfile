pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing HTML project...'
            }
        }

        stage('Package') {
            steps {
                sh 'docker build -t devops-html:${BUILD_NUMBER} .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker stop mywebsite || true
                    docker rm mywebsite || true
                    docker run -d -p 8081:80 --name mywebsite devops-html:${BUILD_NUMBER}
                '''
            }
        }
    }
}