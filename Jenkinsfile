pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code checked out from Git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building FastAPI application'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
            }
        }

        stage('Build Image') {
            steps {
                echo 'Building Podman image'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
            }
        }
    }
}
