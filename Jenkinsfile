pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/ahmdfauzi2004/bnsp.git'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh '''
                echo "Stopping old containers..."
                docker compose down || true

                echo "Building new containers..."
                docker compose build

                echo "Starting containers..."
                docker compose up -d
                '''
            }
        }
    }
}
