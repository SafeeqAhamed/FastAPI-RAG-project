pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                bat 'pytest'
            }
        }

        stage('Build Image') {
            steps {
                bat 'podman build -t fastapi-rag:latest .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'podman stop rag-api || exit /b 0'
                bat 'podman rm rag-api || exit /b 0'
                bat 'podman run -d --name rag-api -p 8000:8000 fastapi-rag:latest'
            }
        }
    }
}
