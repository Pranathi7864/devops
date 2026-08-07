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
    }
}